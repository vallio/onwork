+++
title = 'So what exactly do you do ... (PM Edition)'
date = 2025-08-29
draft = false
tags = ["Microsoft"]
weight = 10
+++
My 22 year old son asks me “so what ***exactly*** did you do at Microsoft?”. He doesn’t want to know what products I worked on or results achieved, but what my actual work was. And I am at a loss on how to respond which means I was either really bad at being a Program Manager or really good at it.

Over the years, I’ve heard variations of this question from parents, siblings, friends, interviewees. I offered up variations of unsatisfactory abstract answers 

- *Build and ship the right product at the right time to customers who love it.*  
- *As part of the engineering team, be the voice of the customer*  
- *Be the CEO of the feature, feature area, or product.*  
- *Be the glue, do whatever is needed.*  
- .. and so on

Before I joined Microsoft, I was primarily a developer and it was easier to explain. Coding is concrete, at least it seems that way to me. When I joined Microsoft as a PM in 2005, it was a bit of a mystery to me what job role I was taking on. At first, I pretended to know while frantically studying all the MS internal collateral I could find. There was an engineering excellence guidebook that walked you through what the PM did at each stage of the development cycle, there was the Tao of Program Management paper, there was the Sinofsky [post](https://web.eecs.umich.edu/~weimerw/2022-481W/readings/PM%20at%20Microsoft%20%E2%80%93%20Steven%20Sinofsky's%20Microsoft%20TechTalk.html) which we read like the bible, and there were these fabulous internal videos by Scott Berkun. Berkun would publish the definitive PM book, “The Art of Program Management" which in later editions he sadly replaced “program with project”.

I started to ask my Beijing PM colleagues about the PM role and it all seemed quite different depending on their specific projects. Even with the most common aspects, project management, the tools, process, and expectations varied wildly. And project management was probably the least interesting part of it to me. What was and remains the most interesting to me is building product (which again, makes me a great or horrible PM). Everything else is collateral. Of course it has to be the right product. Of course it has to meet customer met/unmet needs. Of course it has to be high quality. Of course it has to leverage/contribute to the work of others. Of course it has to be shipped at the right time. 

As a PM, my “in” to building a product was the mythical spec. Early in my tenure at Microsoft, I had the opportunity to work with multiple project teams \- MSN Music, Shopping, MSN/Live Search, Real Time Communications amongst others. I would use the time with Redmond peers to ask the same question my son asked me “what do you exactly do as a PM” and the worst/best answer I got was from a shopping team PM “yea, I used to ask that when I was new to role too”. I shifted my strategy to ask “what makes a good spec” and that didn’t prove so useful either. I took the MS spec writing class that was heavy on the process of spec writing and light on concrete examples I could use for my actual spec writing. I was particularly curious about the level of detail to be covered in each section of the spec.

I changed tactics again.. I asked for examples of specs a peer found to be good and I got all kinds of documents back. For search, it was a technical spec stored in Source Depot. For shopping it was an unachievable deck and a work in progress doc. For realtime communications it was more structured but a little too abstract. I found spec adherence by the engineering team to vary widely. Widely, as in some teams had a rule that if it wasn’t in the spec it wasn’t in the product while other teams paid little attention to specs written by PMs. There were specs as “living documents” (which sometimes meant unfinished) and change controlled specs (which sometimes meant high friction to change). 

As I write this, I realize I too am being too abstract. To answer my son's question, “What exactly did you do at Microsoft”? A reasonable place to start might be with the idealized work week, which for me would be something like:

80 blocks of work, 30 minutes each.   
08 \- Email triage and response (30 minutes every morning, 15 minutes in afternoons)  
16 \- Meetings focused on decision making or collaboration   
04 \- Meetings focused on information sharing   
08 \- 1:1s with team members  
06 \- Deep work, research   
06 \- Deep work, design   
06 \- Deep work, writing and rewriting   
06 \- Deep work, customer and market understanding   
04 \- Recruiting and interviews  
04 \- Management overhead   
05 \- Reflect and plan work for the next day  
07 \- Randomization, socialization, and corporate time   
   
I call it “idealized” because it almost never happens exactly this way and you end up needing to prioritize your time intentionally or unintentionally. I highly recommend result focused 30 minute blocks. 

Somehow, this still don’t feel this is a very satisfactory answer, so I’ll unwind a specific project:

Office WebApps and PowerPoint Online (2014-2019)

* Our 60 person team reorged into this project with the stated goal to close the feature gap between the desktop and web clients. There was some people churn and uncertainty and I felt we really needed to get our team focused and making progress. Feature prioritization included customer importance and getting the team ramped up on different areas of the technical stack. Features like word count, insert image/video, copy/paste, gridlines, and many more. There were discussions to get stakeholders aligned on the list and buy-in with timelines from the engineers doing the actual work. When our involvement in the project wound down in 2019, I looked back at that original feature list we delivered and it was one the most significant team accomplishments I’ve seen.   
* As a Lead PM, I showed my team what I expected in a spec by writing one for the image/video features and using that as a recipe for execution. Led the features through ship criteria discussion including A/B testing which was new to the team.  
* Read the customer feedback verbatim and internalized the quality issues our customers were experiencing. It informed the product vision document we drafted which captured the importance of PowerPoint on the web being a “PowerPoint that just worked”.  
* Did data mining to get real user behavior data with a focus on coauthoring usage.  
* Every quarter or so, would share the results from the previous quarter and the plans for the next quarter. The sharing would be in a variety of formats \- at team wide meetings, in small stakeholder meetings, in exec reviews, and so on.   
* Daily triage of bugs as we got ready to ship a new front end framework. There were a lot of bugs and along with engineering counterparts we decided which needed to be fixed for each release stage.   
* Used our products for real work every day.  
* Used our competitor products regularly.   
* Respectively stood up to HQ when they said things that only made sense in an alternative universe. Example: “Coauth is supported\! File a bug of not working.” except the “working” wasn’t what any customer would expect. Max of five coauthors. No presence indicator. And even this crashed most of the time. After we worked on coauth, it supported 50+ users with a realtime presence indicator including typing.   
* Many alignment discussions. Sometimes being aligned to a partner effort we needed to support, sometimes aligning partners on an outcome we were driving.   
* Many, many, other activities \- customer visits, brainstorming, etc. 

Still not sure if this is a satisfactory answer. Will need to check with my son. 