---
title: "Learning Go"
date: 2024-08-27T08:32:11-07:00
draft: true
author: "Yes Way Jose"
cover: 
  image: "img/Go-Gopher.jpg"
  relative: false
---

I have been an official Go programmer for three years now. Unlike many people in my team, I remember the day Google announced go. I don't remember if it was in Hacker News or /programming reddit, but I do remember watching the go math package compiling in less than a second, at the time, I was writing C++ for an embedded system. Building the whole model as we used to say took 45 minutes, this compiled our C/C++ project into a .out file for an ARM9 and a C55 DSP. When I saw how quickly Go built I was like, wow. To be fair, our build was for a Real Time OS so it didn't even include the C++ standard library. Most of the time, if I remember right, was spent linking everything. THe linker was getting it's poor butt kicked. Anyyway, I looked at Rob Pike (?) on YouTube and I was like, 

Anyway, fast forward a few years to 2021, I'm in Seattle, working at Amazon on the retail website. I had recently implemented a simple job that does a very simple thing, I did it as a Lambda function in go. The Senior Devs in my team gave me flak for picking go as the language, citing that we are a Java shop and we are not guaranteed to have developers that can maintain a go package. Fair enough, but I pushed back saying that this particular thing was so simple, and the go implementation is so much less verbose. The Lambda was pushed to prod, but I was just a bit frustrated. Then I got an email from a manager in AWS asking me if I'd be willing to join his team, where they are looking for Gophers. 

So yeah, 3 years ago I switched to AWS Fargate where I get to work on the Fargate Agent, the not-open source version of the ecs-agent. 

So, all that to say, I'm still learning. I'm still learning go. I like how it is easy to get started on this language, but there are things that I still wrestle with. 
I still don't really get interfaces, so I am working on that. Just now I was reading about [Interface Pollution](https://100go.co/5-interface-pollution/) So hopefully I'll have a deeper understanding of not only how to write interfaces (failry easily) but understand how to do it [idiomatically](https://go.dev/doc/effective_go) as well as **understand why they designed the language this way in the first place**

Thank you [Julia Evans](https://jvns.ca/blog/2024/08/06/go-structs-copied-on-assignment/) for writing about go in your blog. And I can't recommend [100 Go Mistakes and How to Avoid Them](https://100go.co/) enough. 

So, a few weeks ago I wanted to write a deep dive into Go Concurrency, but then life happens and it got abandoned. I'll finish the article and post it here. 

-JV