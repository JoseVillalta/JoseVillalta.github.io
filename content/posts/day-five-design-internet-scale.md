---
title: "Paper every day. Day Five: On Designing and Deploying Internet Scale Services"
date: 2022-07-21T07:07:19-07:00
Author: Jose Villalta
---

[Link to Paper](https://s3.amazonaws.com/systemsandpapers/papers/hamilton.pdf)

This paper is a list of recommendations for running a large-scale system that aims to keep quality high and costs low. The author comes from the Windows Live Services Platform but this might as well be read as an Amazon internal guide since I didn't see a thing in this list that we don't do (or aim to do) in AWS. EDIT: Of course all these things sound familiar! The author is [James Hamilton!](https://perspectives.mvdirona.com/) He's a VP and distinguished engineer here at AWS, I know him from leading the weekly AWS Ops Review meeting. 

I enjoyed the focus of quality to number of administrator ratio, this is the realistic view of the world as cost drives a lot of technical decisions whether we want to or not. I also enjoyed getting the rationale for decisions we take for granted, like why we want to have a single version of the service deployed (excluding blue/green deployments) If a business wants to keep operation costs low then maintaining multiple versions of a system is not scalable.  One thing that is very Amazonian listed in this paper is the fact the teams that operate the service in prod is the same team that developed the system, this paper notes that the more separation between development and operation teams, the higher the overall cost in time and effort. 

This paper is filled with goodies, so I am going to bookmark it. 

Here's the outline:

### Overall Application Design

- **Design for Failure**.  Core concept. Your components WILL FAIL. It's better to decide ahead of time how your system will react when (not if) that happens. 
- **Reducdancy and fault recovery**. This is also bread and butter at AWS. We aim to design the system such that any subcomponent could crash without affecting other components so that we can gracefully degrade. 
- **Commodity hardware slice**. This is the interesting thing about the cloud, something that the big cloud providers realized early on is that it's cheaper to buy large clusters of 'commodity servers' (translation: cheap computers) that a small numbers of super-computers. The thing I didn't think about this cost includes power costs (it increases linearly with more servers but cubically with clock frequency, duh!) as well as I/O performance. Since I/O perf becomes the bottleneck as computing power increases. 
- **Single-version software**. Like i said earlier, this was very interesting to me. Fromt the paper: "The most economic services don't give customers control over the version they run, and only host one version" This is an obvious but profound statement, there's only one version of EC2 running. I mean, you can request different type of servers, but if you need to lock down a specific version of the system, then I think you can host EC2 on premise, but that's about it. 
- **Multi-tenancy**. Multiple users on the same (hosts/AZ/Region) keeps costs down. Giving the end users the illusion that their task is the only one running on the system is hard to get right 100% of the time, my job at Fargate is to keep the 'number of nines' high. The scale in which the cloud operates makes it a big challenge. If our service works only 99.9% percent of the time, then the number of users affected is unacceptably high. 


#### More specific list of design recommendations

- Quick Service health check
- Develop in the full environment. (Test what you ship. Ship what you test)
- Zero trust of underlying components (+1000)
- Do not build the same functionaliyt in multiple components (Distributed DRY?)
- One pod or cluster should not affect another pod or cluster
- Allow (rare) emergency human intervation. (emphasis on rare)
- Keep things simple and robust
- Enforce admission control at all levels (Underated recommendation)
- Partition the service (so that you can scale)
- Understand the network design (this is the most challenging for me, personally, even with all my experience I still think the network as a magic black box)
- Analyze throughput and latency 
- Treat operation utilities as part of the service. (Another thing that sets AWS apart IMO, Operations Excellence is understood to be the most important aspect of the service)
- Understand access patterns
- Version everything
- Keep the unit/functional tests from the previous release
- Avoid single points of failure


Other factors to consider is automating as much as possible, make the development teams responsible for operations and capacity planning and an excellent section on Dependency Management. 

### Conclusion
I will share this paper with the team since this paper contains the blueprints for Amazon's culture of operational excellence. I was happy to realize I knew who the author is. Fun fact, last time I heard from James he was in a boat navigating the world, I was in a meeting where he dialed in from his boat in the middle of the Pacific Ocean. I thought that was super cool. 