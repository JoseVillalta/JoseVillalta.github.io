---
title: "Paper every day. Day Two: Kubernetes"
date: 2022-07-18T06:33:49-07:00
Author: Jose Villalta
---

<h1>Borg, Omega and Kubernetes. Lessons learned from three continaer-management systems over a decade</h1>


Welcome to day 2 of my paper-every-day journey. Today we're going to cover [Borg, Omega and Kubernetes](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/44843.pdf) This paper goes over how Kubernetes, the de-facto, open-source orchestrator of containers was developed using the lessons learned from building Borg and Omega, Google's internal job orchestrator. 

Kubernetes is a container orchestration system that aims to make developing and deploying complex distributed systems easier. 
The Borg and Omega papers are excellent papers on their own right, but this explanation original published in ACM Queue is very insightful. These are the lessons I gathered:


- Maintain flexibility and scalability by breaking up the system into small components that only do one thing and can be used as building blocks

- At the same time, enforce a consitent approach to APIs. For example all K8's objects have 3 fields: ObjectMetadata, Spec and Status. Having both uniform and extandable API's is very powerful since it lets your users adopt your system by learning it faster and giving them the ability to customize K8s to fit their needs.

- Shift the focus from managing machines to managing applications.  I take this for granted now, because that's we've been developing for years here at Amazon, but the applications is the thing we care about, not the machine in which it is running, we track task ids, and that's what we use as the key to see status, to look for logs, this decoupling fromt he machine that runs the application give eveyone a lot of advantages. 

- Don't mess with DNS. The K8's team decided to give an IP to the Pod. Networking in Containers can be hard. Trust me. 

- Configuration can be difficult, thankfully the [OCI standard](https://opencontainers.org/) helps. 

- I didn't realize it was google who "invented" Linux containers...at least they contributed the code to make cgroup a Linux thing. Good on them. 

- K8's appears to be a happy medium between Borg's monolithic API approach and Omega completely decentralized system. 

As a personal note, I remember being at the Google campus in Fremont (Seattle) when I first heard of Kubernetes this is around 2014, I remember hearing about it and realizing that it was going to be a big deal. I guess I was not wrong, nowdays Kubernetes is very popular although I hear that it's complex to use. I personally have not used it much beyond the tutorials but ECS and Fargate solve many of the same problems K8's solves, albeit, a little differently. 


Well, I got to get my real job, so that's it for today. Excellent read. 10/10 Would read again. 