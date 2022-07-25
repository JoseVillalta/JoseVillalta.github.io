---
title: "Paper every day: Day Nine: An Analysis of Linux Scalability to Many Cores"
date: 2022-07-25T09:13:41-07:00
author: Jose Villalta
tag: Linux
---

[Link to Paper](https://pdos.csail.mit.edu/papers/linux:osdi10.pdf)

From the abstract:

"This paper analyzes the scalability of seven system applications running on Linux on a 48-core computer...using mostly standard parallel programming techniques -this paper introduces one new technique **sloppy counters** these bottlencek can be removed from the kernl or avoided by changing the application slightly"

This paper has an excellent system level tutorial on scalability. They explain that you don't get linear increase in performance because in real life applications parallel tasks usually interact, an interaction forces serial execution. Then they list the common causes with common solutions. This paper is throughly written and researched. Writing truly parallel code is difficult and even then applications still compete for some shared resouce, be it a local cache, network access or disk I/O. 

The authors introduce the concept of **sloppy counters** which avoid the bottlenect that occurs when Linux uses shared reference counters for garbage collection and managing various resources. The authors report bottlenecks from reference counts on directory entry objects (dentrys), mounted file system objects (vfsmounts), network rounting table entries and counters traking the amount of memory allocated by each network protocol.  

Figure 1 in the paper provide a summary of linux scability problems that it's worth using as a reference

- Parallel accept
- dentry reference counting
- vfsmount reference counting
- IP packet destination reference counting
- Acquiring dentry spin locks
- mount point table spin lock
- Adding files to the open list
- Allocating DMA buffers
- False sharing in net_device and device
- False sharing in page
- inode lists
- Dcache lists
- Per-inode mutex
- Super-page fine grained locking
- Zeroing super-pages


