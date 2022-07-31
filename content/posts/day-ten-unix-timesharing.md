---
title: "Paper every Day. Day ten: The Unix Timesharing System by Dennis Ritchie and Ken Thompson"
date: 2022-07-31T10:40:30-07:00
author: Jose Villalta
---


[Link to Paper](https://dsf.berkeley.edu/cs262/unix.pdf)



This paper, published in July 1974 is remarkable because the design decisions that were made back then by these guys working at Bell Labs on an operating system for the [PDP-11 ](https://en.wikipedia.org/wiki/PDP-11) are still relevant.

I am still struggling to create a mental model of the unix file system, the fact that it looks like a single tree with the root at the top while simultaneously you can have multiple devices [mounted](https://en.wikipedia.org/wiki/Mount_(Unix)) dates back to these guys at Bell Labs. 

There's many things that this paper does for me, how did these people do it? is there anything special about them that make them create things that live on or is it that they were at the right place a the right time? Are these system design decision special and proven by the test of time or these arbitrary decisions that were made famous because this system was shared with Universities in the begginning?

I think it's a bit of both, I think that had the Unix file system been hard to use, understand or modify, it wouldn't be here anymore. However I don't belive it's the ONLY way to make a system work. 

Anyway, the paper is a good read, a lot of the things mentioned will be familiar to you if you are a Linux user. This paper will be 50 years old in 2 years and yet it's still relevant. 

Great read. 

