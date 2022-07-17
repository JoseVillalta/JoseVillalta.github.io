---
Author: "Jose Villalta"

title: "Goal: A Paper Every Day. Day 1: Mesos Paper"
date: 2022-07-17T13:04:01-07:00
---


I've decided to read a research paper each day. I am doing this in order to get better at my craft. 
I want to be better at designing software and it has been shown in research that the people who are really good at what they do
are those that do "delibarate practice" I am most definitely NOT the best software system designer out there, but talent is overated and I 
intend to improve my knowledge one day at time. You are welcome to follow along. 

I'm not the first person to come up with this concept. That would be [Adrien Coyler](https://twitter.com/adriancolyer) from [the morning paper](https://blog.acolyer.org/)]). Sadly, after 10 years going strong, Adrian stopped posting last year. 

So without further ado, let me briefly mention the first paper: 

[Mesos: A Platform for Fine-Grained Resource Sharing in the Data Center](https://s3.amazonaws.com/systemsandpapers/papers/mesos.pdf)

I chose the Mesos paper because the domain is close to what I do at my day job. I work for Fargate, which is the serverless offering at AWS's Elastic Container Service. 

[Mesos](https://mesos.apache.org/) is an open source platform for running tasks in a distributed system, it abstracts away physical machines by exposing a computing model where you define the computing resources you need (CPU, Memory, storage) and you program against it. Pretty much like Fargate :) 

The paper talks about the challenges of matching user's tasks to available computing resources and rightly conclude that there is no single scheduling algorithm that will be efficient 100% of the time. Mesos addresses this issue by delegating the job of fine-grained scheduling to the execution framework, Mesos Clusters can host more than one framework thus giving it flexibility and increasing the utilization of the compute fleet. 

Mesos breaks up the system into one leader process that manages multiple worker deamons. Each daemon runs a framework that executes each tasks. The main abstraction for sharing resources among frameworks is called "resource offers" Each resource offer contains a list of free resources on multiple workers. The leader decides how many resources to offer each framework based on configurable policies. 

A framework that runs on Mesos consists of two main components, a scheduler and an executor. 

The interesting thing about the paper, and what I like about it is that even this approach does not always work, the authors evaluated Mesos by running multiple frameworks and comparing the performance, they introduced a new framwork called Spark that is specialliced for certain kinds of computing jobs (In this case linear regression)

Funny enough, I have had some experience with these systems, back when I was part of Impinj's DevOps guild we had a consultant come in and introduce Mesos to us, at that time we were in the middle of refactoring our monolithic system into microservices and this was the layer that would orchestrate our system. I used Spark at Amazon when I was tasked with "fixed the Machine Learning Model" for Mexico. We have a big job that traverses the retail catalog for the Mexico retail site, making sure that if the page is configured in Spanish, that it is actually in Spanish. We used an NLP tool for language detection that was working just fine but the business team was convinced had a bug in it because the false positive rate was too high (It turned out to be a logic bug not a bug in the tool) it was the first time that I had to work with a tool that crunched over millions of data records, it was intimidating at first I'm not going to lie. 

Anyway, if I'm going to do this on a daily basis, I better keep it short. So long, till next time (hopefull tomorrow)

