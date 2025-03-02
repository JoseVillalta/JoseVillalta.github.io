---
title: "How do you architech change? The answer is simple, but not always easy"
date: 2025-03-01T16:13:55-08:00
draft: false
---

This week I had an Eureka moment at work. You see, there are many things I see at work that I would like to improve. Technical debt in our codebase. Inefficient processes. Communication silos across teams. The list of things one can improve never ends, this is true in all software shops. System complixity grows as new functionality gets added, inefficiencies optimized, bugs fixed. Secuirty hardened, etc. 

How do you increase the quality of your system without interrupting the flow? Well, obviously, you break it up, one tiny thing at time. That's how. Yeah it's obvious but (this is embarrasing to admit) I get the urge to make BIG changes, I'd like to rewrite whole chuncks of the codebase, I'd like to build a brand new release pipeline, and we might do that someday, but not today. When you have a team that's busy doing the work, tidying up gets deprioritized. After all, that bug in prod needs to get fixed yesterday, that new feature needs to ship on time. Oh, by the way, the developer that was working on that thing your system depends on quit last week. 

So the solution is to **constantly** improve, to have a clear vision, a clear direction, something that's easy to remember and then, you break it up into the **smallestt change possible** and you do one thing at a time. My team has been doing that for production issues, we review our ticket queue every day, we monitor the rate of issues, the age of issues and we look for patterns. 

I want to completely eliminate all manual toil we have to do when we have to deploy a new version of our system to production (we're not a web service per se so Amazon's great tooling doesn't really work in our case) I've been trying to push big changes to the process, but this is proving to be difficult. I am going to try this strategy and see how it works out. Small, constant improvements over big changes can help you evolve your big distributed system. 

The thing that most people don't realize when you are in the business of building big systems is that ideas are cheap, there's no shortage of ideas, but what matters most is execution. Small incremental change is always better than big rewrites. 

-JV



