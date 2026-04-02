+++
title = 'Building an App and The Creative Gap'
date = 2026-01-15
draft = false
tags = ["Culture", "Creating"]
weight = 10
+++
If you’re a creative, you know the gap between the vision in your head and what you actually build. You may end up disappointed, frustrated, delighted. The gap gnaws at you and forces you to either give up or close the gap. I am working on closing that gap.

Recently, I was looking for a project to work on. I wanted to feel productive and to me that mostly means creating.  I listen to a ton of podcasts and I also like True Crime. I brainstormed a bit with ChatGPT and landed on an idea \- wouldn’t it be great for the True Crime cases that really interest me, if I could get a feed of new podcasts and other case updates on my phone?

This is why I ended up building an iOS app called “[True Crime Atlas](https://apps.apple.com/us/app/true-crime-atlas/id6756570206)” and a companion website [https://truecrimeatlas.net](https://truecrimeatlas.net). Did I realize my vision? Not exactly, Am I pleased with the result? It’s complicated. I am grateful for the work. 

I didn’t write these down at the time, but I had some guiding principles:

- I’m cheap. This meant using free tiers of ChatGPT, MS Copilot, and Gemini. It also meant no dynamic serving of content until after the App proved itself. I wanted everything generated at build time.   
- No competitive analysis or market research. I was doing this project for fun and wanted to see where my instincts took me. I didn’t want to be influenced by what’s already out there. Not yet.   
- The data \- what would become the case file \- was the key problem to solve.  
- Deal with monetization later if there’s an audience for the app. 


Lessons I learned along the way

- Going from 0-1 with the free tiers is ridiculously easy. With some guided prompts, I was able to develop the case file format, the supporting Realm schema/loader, and the iOS app quite quickly. When I decided to build a static web site using the same case file content, it took less than a day with the free tiers.  
- I found using prompting in the free tiers was more natural and productive than using a fancier agent driven tool such as Antigravity.   
- It felt very natural to use the free tiers for different purposes. ChatGPT as a kind of senior mentor and advisor. MS Copilot to build out the apps and initial case files. Gemini for code iterations and case file building.   
- When iterating, AI chat in VSCode and XCode was a godsend. Small changes could be done very quickly and even large changes, with the right context went very smoothly.   
- When iterating, AI chat in VSCode and XCode was a disaster. Sometimes the model decided to rewrite code and drop functionality. Sometimes the model would be very stubborn on technique. For example, in order to make my Realm DB access thread safe, the model kept suggesting/writing DTO (Data Transfer Objects) but I didn’t want to add that level of complexity.   
- I went through several techniques to build the case file. I ended up using a Gemini in deep research flow that allows me to create/update case files relatively easily.   
- Curation of the case files themselves takes more time than I would like (broken media links). I ended up building a visual tool for editing the case files.    
- The “aha” moment when I stumbled upon the location view.  
- A fan of VSCode, not a fan of XCode. 

There are still a bunch of things that are gnawing at me in order to get closer to the vision. Would love to hear suggestions. 

When I first started working a middle aged coworker decided to quit his job and focus instead on writing novels. He told me that he needed to be creative and being a programmer allowed no room for that. At the time, I didn’t get that. I always saw programming as a creative pursuit. For some, I can see how constraining it can be. My challenge remains that gap. A delight is in closing the gap the vision also evolves. 

