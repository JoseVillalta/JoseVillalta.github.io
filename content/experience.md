---
author: "Jose Villalta"
title: "Professional Experience and Education"

cover: 
   image: "img/spheres.jpg"
   relative: false

---


## Summary

#### Amazon 2018 - present

- AWS Fargate: Dataplane team. Writing Golang mostly. 

- Worked on retail site for 2.5 years using the away team model. 


#### Impinj 2014 - 2018
-  Wrote Ruby on Rails


#### Motorola 2007 - 2014
- Low level firmware


#### Co-op Intern at IBM 2005 - 2006
- ASIC design model testing


## Education

- Master's Degree in Electrical and Computer Engineer from the University of Florida
- Bachelor's Degree in Computer Engineering from Florida Atlantic University

## My Career Journey

This is a more detailed narrative of my carreer so far. I've been lucky to work on cool projects solving interesting problems. 

#### IBM 2005-2006 Co-op Engineer Internship. Rochester, MN


My career in tech started with a firm handshake.

When I was in college a friend of mine urged me to join SHPE, next thing I know, I’m at a SHPE conference in Philly. The year is 2005 and I had just returned from a 15-month Iraq deployment. I found myself at a conference hall with hundreds of other college students at a career fair. The biggest booth there was the IBM booth. There was a long line of students eagerly waiting to submit their resumes. Most of the students there were from big name Universities, I can still see the Georgia Tech students with their bright yellow polo shirts I was just one more student from FAU. I notice there’s a guy walking around chatting with people. I suddenly stepped out of line to shake this man’s hand. 

“Hello Sir, my name is Jose Villalta. I have a couple of things to tell you about me. I am a war veteran, I work full time to pay for school, I am enrolled full time at FAU and I have a 3.8 GPA, my dad worked for IBM in the seventies, I’d love to work for IBM now”

The guy looks at me, looks at my resume and he says:

“What do you want to work on, Software or Hardware?”

I really wanted to say “I’ll do anything” but then one word sealed my fate:

“Hardware”

This man, gave me his business card and told me to tell him what I just said to him in an email and he’ll take care of me. 
I did, and after a round of interviews in Dallas I got a job offer to work for the ASIC Design group at IBM. 

Internships usually last 12 weeks and are generally done over the summer. This was a six months long full-time gig. I was on site working alongside the folks that design processors, motherboards or chipsets for various products. My building housed the teams that worked on the processors and chips that powered mainframes, the cell processor that powered the X-box and play stations and others. My job was to write software that parsed requirement documents and generated test cases. I also re-factored a factory tester script that executed in the “fab” to make sure the silicon wafers that contain our chips still work. I wrote perl and Unix bash but the domain was very, very low level. Logic gate level stuff. Testing that AND gates behaved like AND gates and OR gates behaved like OR gates.  

When my six months were up, I wanted to keep doing the job forever, so I asked if they’d let me work remotely and they said yes. (This is 2005 so it was not a common practice back then) 


I stayed in that group for one and a half years. I was planning on coming in as a full time employee and moving to Rochester but the department I was on got cut in half Q4 of 2006. One half was let go (I was not let go b/c I was an intern) and the other half was told their job was going to be moved to a different site in another country. 





#### Motorola 2007-2014 Firmware Software Developer. Plantation, FL


My first job out of college was writing embedded software for the “low-level” team. I was brought in as part of a new hire wave to work on a new radio product.  Project Mackinaw:  The “APX” series radios. The previous projects were all in C and Assembly this new project was implemented in C++

 I was assigned to the “low level” team working on the “RF Deck” My code interacted with the hardware abstraction layer (HAL) mostly drivers for RF chips. I learned a lot working there. I learned to apply real-time operating system concepts, memory and power constraints. My component was all about controlling and configuring the RF hardware with precise timing in order to support APCO radio protocol (Think police and firefighters walkie talkies). I worked on that product from design to launch and then stayed for new releases and features for about 7 years. 

I learned C++ there, but not how most people write it. Our team was doing this thing where theoretically we draw UML and this tool (IBM Rational Rose) would convert the UML to C++ code that will then get compiled down to .out files executable on the board. The UML to C++ thing was...uh, one way to do it. I didn’t know any better since this was my first gig out of college I never thought there was something off with doing things that way and never questioned it. Source control was not .h or .cpp files, instead the source code was in ...XML. Machine-generated XML to be precise, this was not optimal when doing file merges. The tool was slow and it would crash if the xml was not properly formatted. 

I did love working there though. I made life-long friends in that team. I learned a lot about radios, signal processing, information theory, wireless communication as well as software engineering processes. Lean sigma, and much more. 

The best boss I ever had was my team lead, mentor then manager and now VP Martin Elmore. When I was a new hire he gave me one valuable lesson: “Catch your own bugs first, don’t let other people find your bugs” 


#### Impinj 2014 - 2018 Seattle, WA

I moved to Seattle to work for Impinj, back then it was still a VC-funded startup that designed and built RFID chips. I was hired to work on a new version of the factory tester software. A C++ application that validated the silicon wafers in our "fabs" after that project completed I found myself part of the "Factory Services" team. My new system's job was to ingest all the data generated during the manufacturing process (test results, location, quantities, status) in order to support the engineering team, the operations and business team. 

The system was a set of Ruby on Rails applications backed by a MS SQL database. This was my first time writing code that worked by communicating with other computers connected via a network. Computers distributed across the globe that needed to coordinate and present accurate data to our customers. 

Once again, my career took a turn on a lark. I volunteered to be the "Dev Ops" person for my team, without really knowing what dev ops was. 

I quickly immersed myself in the world of containers. As a sidenote I remember going to a tech meetup hosted by Google in their Fremont campus. I heard a presentation about an exciting new tech to orchestrate containers called Kubernettes. I understood back then that this tech would influence how people run containers but I thought it was too complex for our use case at work. I worked on the effort to break up our rails services so that each can get deployed seperately in their own VM as opposed to having a single server hosting every app. I used docker swarm for the orchestration. Chef and Ansible for Infrastructure management. 

I learned a ton at Impinj, sometimes it felt crazy to be working on a problem that nobody else had worked on. Impinj is a great place to work with good people and interesting technical problems. 

#### Amazon 2018 - present. Seattle WA

I've been in 3 different orgs in the past five and a half years. I joined EC2 first where I wrote a job to automate the process of mapping new "bricks" (think the beefy computers that power EC2) to their correspoding cells when they are first started in the data centers. I was there for only six months. I was lured to work on the retail side of the business. I went to work for the team that expanded retail to North America and Latin America. 

The "NARX" team operated as an away team. Meaning we did not own any specific tech per se. Instead we were tasked with expanding the business to new Marketplaces. Say that we wanted to offer one-day shipping in Mexico, our team would learn all the systems involved on making that happen, and it would make the changes and the host team just had to approve it. I was exposed to a lot of different tech. I worked on projects related to payments, accounting, search, catalog, delivery experience and more. I worked for an awesome manager with awesome people. 

In 2021 I was presented with the chance to return to AWS. I wanted to settle down and work in the container space, something I have been passionate about since my days at Impinj. So I went to the AWS Fargate team working on the Dataplane. I worked as part of the Fargate Agent team, the process that orchestrates containerized apps on behalf of our customers. I write golang (and some Rust) and I get to work on system-level software at a large scale. I love it most days. I should say more but it's still early