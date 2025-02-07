+++
title = 'Project - Out of order'
date = 2025-02-05
draft = false
tags = ["BofA", "Projects"]
weight = 10
+++
The well worn dot matrix printer is connected to the 10 million dollar mainframe. We are single step debugging at the machine level and printing diagnostics. The diagnostics are for the microcode engineers back in Japan. The breakpoint hits. We execute the instruction. Ok. The next instruction XORs memory on itself (leaving 0s) followed by an instruction that restores the memory to the original value. The sequence is there to trick the system into thinking something changed so the memory won’t be paged out. We step into the XOR instruction but instead the system executes the one after it. Hmm.. did we all miss something. Then we execute the next instruction but the system goes backward and executes the XOR. It executed the two instructions out of order. That is not supposed to happen and blew my mind. And worse for our users, it left the 0s in memory instead of what should be there. And the 0s were a problem.

How did we get here?

It is 1995 or 1996 and I had just been promoted to Consulting Systems Engineer at Bank of America. It was the part of my career where I could do anything but not aware that I could. I was assigned a project to merge our ADF2VM and ABACIS2 mainframe systems. 

For capacity and location reasons, BofA had a handful of VM systems. ADF2VM was primarily used by developers and ABACIS2 was primarily used by information workers. The separation by function was in part due to capacity constraints \- we could not buy a single mainframe to host both workloads. But that had changed by 1995 and in fact ADF2VM and AVACIS2 were running on the same hardware which had been physically partitioned to run the workloads independently. The obvious thing to do, someone not me realized, was to run a combined workload on the whole machine which would ease growth constraints. My job was to make that happen. 

I started by doing an inventory of the kinds of applications on the systems and if any barriers to running. The main challenge was names. The host names themselves were hard coded in a bunch of places and some names, like user accounts, collided with each other. It was fairly straightforward to come up with a set of rules that could handle 95% of the cases. Getting people to update their scripts, mostly EXEC2 and Rexx, was challenging. We decided to do it for them. We had some code that could link and scan code for every account. I added the part where we would change the code on their behalf. We informed the users we were going to do this in order to give them a chance to opt out and handle it themselves. Surprisingly, few of them did. 

So after months of planning and tool development, we executed the merge over a weekend. It went about as well as I could expect and come Monday morning, I was feeling good \- we’ve just merged two very large mainframe systems into one. Then we got a call that a Nomad database crashed. Odd, but they do crash from time to time. Then more reports came in. Did Nomad have an upgrade? No. Can’t be related to the system merge, could it be? Just in case, we looked at some of the dump files. What did we find? “00000000” where code was expected to be. No pattern in the code, just the zeros. Then other apps reported crashes and also showed the zeros. What was going on?

Our first action was to scan all Nomad databases for zeros and we extended out. We found many cases. The problem was getting worse, so we shut down system access for normal users. About 5000 information workers and developers were on hold until we could figure it out. And to further complicate, there was no feasible way to back out. 

It was a Sev 0/1 situation and one thing I learned is some people stepped up to help, and some people stepped back. And it was not who I expected. The person I learned the most from and who I thought was the most capable, stepped back. The person who I thought was not so serious about work, got very serious and stepped into the problem. 

It was he who had the sense to scan the operating source code (yes, we had the VM/CMS source code) for where it wrote zeros. One hit, in the VM control program where it wrote 0s to memory and then restored the original value back as a way to keep a page active. I read the code. Others read it. It should not cause the problem since the memory was restored in the next instruction and thread safe wasn’t a concern at this level. 

We tried a few things..I forget exactly what..but probably some logging at the CMS level to catch any other possible culprits. This led to the control program code as the remaining suspect, but it didn’t make sense. Still, we decided to debug it and saw the out of order execution which resolved the mystery. 

The mainframe we were using was an IBM compatible one, manufactured by Hitachi. When we learned it was a microcode issue, a BofA exec demanded the Hitachi engineers who were actually working on the problem get on a call and explain what was going on. The engineers found the bug and fixed the microcode before the call ever took place. A second mystery: why were we seeing this error now? It turns out we were the only shop in the world running VM/CMS on this specific Hitachi configuration. 

