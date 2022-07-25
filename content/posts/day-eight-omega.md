---
title: "Paper every day. Day Eight. Omega: flexible scalable scheduler for large compute clusters"
date: 2022-07-24T21:30:27-07:00
author: Jose Villalta
---

### Omega
[Link to paper](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/41684.pdf)

Omega was the second cluster manager system built by Google. It is Borg's sucessor and it was designed as a happy medium between Borg's centralized scheduler architecture and Mesos's two-level approach where the placement is delegated to the running framework. Omega shares the state of the cluster among leaders and uses optimistic concurrency control (detect when different cluster schedulers are competing for the same resource)

The premise of the whole paper is that a centralized scheduler does not scale well, so there must be a better way to handle scheduling different types of workloads in a fast and conrrect manner. The two main types of workloads, services and batches have different requriements and present their unique challenges. The paper explains the type of simulations the engineer at Google used to determine that conflicts among different scheduler is not that common and that Omega manages to fit more tasks in the clusters than Mesos. 

It's a good read, although it bears to mention, I'm not sure whatever happened to Omega after Kubernetes came along since I know that Borg is still around. 

In any case. Good paper. 



