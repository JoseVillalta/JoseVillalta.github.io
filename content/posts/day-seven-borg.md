---
title: "Paper every day. Day Seven: Large-scale cluster management at Google with Borg"
date: 2022-07-23T18:56:09-07:00
Author: Jose Villalta
---

### Borg
[Link to Paper](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/43438.pdf)

Borg is the cluster management system that runs hundreds of thousands of jobs at Google, it is the original system, it's sucessor Omega was written as a reaction to the lessons learned from it. Kubernetes is the third system written with the lessons from those two. This paper helped me understand a few things about my own system since we have our own cluster managenet and scheduler system that work a little different but in general do the same job. 

The paper is broken down into 6 major parts

## The user perspective

- Types of workloads. Services that need to always run versus batch jobs
- Clusters and cells
- Jobs and tasks (more similar to ECS than to K8's in my opinion)
- Allocs (interesting concept)
- Priority, quota and admission control
- Naming and monitoring

### Borg Architecture

A borg cell consists of a set of machines with a centralized controller called the Borgmaster, and an agent process called the Borglet that runs on each machine in a cell

- Borgmaster. Controller and scheduler
- Scheduling
    - feasibility checking
    - E-PVM for scoring
- Borglet the agent present on every machine in a cell
- Scalability

This section had a detailed explanation of how they designed the system to make it scale. Some things seem straight forward like breaking up functionality into separate processes that can run in parallel but other things worthy of note was how they cached scores for the scheduler and how they created concepts like "equivalance classes" of jobs in order to make the scheduling calculations simpler. 

### Availability

I paid close attention to this section because, well, I kind of care about making my service available. There is a list of things they did to increase the service availability, like automatically reschedule tasks that were evicted, make requests idempotent, data recovery. There was this thing that caught my attention they state that they remember tasks that failed in a machine, so that they don't schedule the same task/machine combination, and well, I have questions. Doesn't taht get unyieldly? how long do you remember that for? how do you keep track of that? Maybe the way they structured the task book-keeping makes this easy, but to me that seems overly complicated. I wonder if Omega or Kubernetes does the same thing. I cannot confirm nor deny whether ECS does something like this. Okay fine, yes we can do that, but we don't do it at the task to machine level, that is too fine-grained. 

### Utilizition

This section of the paper it's the most detailed and probably could be it's own paper. The authors explain how they used a simulator (Fauxmaster) that used log data from real jobs to compute and predict how many machines are necessary to fulfill the job requests given different system configurations like cell size, cell partitions, and user segragation. Segratatin users would require more machines and therfore cost more. Sharing cells is less costly but the tradeoff is the risk of not isolating workloads from one another. 

### Isolation

Again, there are details about how tasks are isolated from each other. In Borg all the tasks share the same kernel but they run in a container. 

### Lessons learned

There are many good lessons learned here. I have to respect the candor the authors showed when discussing what they would do differently, one thing that resonates is how they regret having optimized for the power users at the expense of casual ones. A lot of the lessons learned from Borg were applied to the design of Kubernetes. 

I really enjoyed the depth of this paper, the authors packed a lot of information to the 18 pages. Good read. 


