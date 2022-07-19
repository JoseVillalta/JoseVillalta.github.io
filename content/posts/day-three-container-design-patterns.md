---
title: "A Paper per day: Container Design Patterns"
date: 2022-07-19T07:23:34-07:00
Author: Jose Villalta
---


### Day three: Design patterns for container-based distributed systems

[Link to paper](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45406.pdf)


Containers provide the ability to package, deploy and reuse applications using a natural isolation boundary. Developers can expose application-specific functionality as interfaces as well as more generic hooks for many systems like metrics, health, etc. 

In this paper the authors present the readers with two types of container design patterns: Patterns for container in the same machine (Single node) and patterns where the containers are spread out in different machines (multi node)

#### Single Node Patterns

***Sidecar Pattern***

Sidecar patterns extend and enhance the main container. A webserver container and logger running alongside in the same machine is a common example. 
Developers could package the whole application as a single container but separating them brings advantages:
- A container is a single unit of allocation for thinking about resource consumptions
- A container is a unit of packaging for dependency management. You can implement your server and logger in different languages or usind different versions of the same libraries
- A container is a unit of reuse. You can write your logger once and reuse it in other applications. 
- A container provides a single *failure boundary* making it possible to degrade gracefully
- A container is a unit of deployment, which allows each piece of functionality to be upgraded and rolled back idependently

***Ambassador Pattern***

Ambassador containers proxy communication to and from a main containers. For example a developer could be writing an application that send data to different services located in different network namespaces the ambassador provides a simple interface to the container to hide away the details of routing request to the appropriate destination. 

***Adapter Pattern***

Adapters present the outside world with a simplified, consistent view of an application for example, exposing metrics to the outside world. It's the opposite of the ambassador pattern in the sense that it simplifies the view of the container to the system. 


#### Multi Node Patterns

***Leader election pattern***

Leader election is a common functionality when replication is used. 

***Work queue pattern***

With containers it should be straight forward to build systems that can act as a generic work queue.

***Scatter/Gather***

Map reduce is an example of this. Clients configure a job, you have one container in charge of sending out work to be done in parallel and the mapper gathers all the results and reduces it down to a single results. This pattern can be applied to many big data applications. 


Personally, I have seen the sidecar, ambassador and adapter pattern a lot but I think the multi-node patterns are examples of things that get implemented once and then become part of the infrastructure, there are multiple systems that implement work queues, leader election and scatter gather, so there is no need to re-implement it when somebody probably has done a better job. 

