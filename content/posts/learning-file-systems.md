---
title: "Learning File Systems"
date: 2023-07-15T21:21:31-07:00
draft: false
---

Lately I have been learning about File Systems from the book "Operating Systems. Three Easy Pieces" by Remzi Arpaci-Dusseau.

I used to think that I knew how file systems worked because the interface open, read and write is so straight forward, what else could there be to it? But then at work some weird issues come up where some weird behaviour happens, like, du says the disk has space but df says the disk is full, what could make that happen? Or when an issue mounting a volume occurs and you realize that you don't know the difference between mounting a block device versus mounting a file system. Are they both the same thing? I need to have a mental model of what the system is doing in order to debug it. Knowing the data structures in the file system and having an idea of what happens when you open a file, how does the operating system find the file? how does it traverse the file tree? What is in memory versus disk? 
I must confess I am still in the dark when it comes to container images and union file systems. I understand how a container is made up of many layers over imposed on top of each other. An image is essentially a tar file of different file systems on top of each other. But, how is it implemented? how do you, can you just put a whole other /proc and other system files on top of a kernel? 
So anyway, that's what I have been up to. 