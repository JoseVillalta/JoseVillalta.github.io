---
author: "Jose Villalta"
title: "Professional Experience"

cover: 
   image: "img/spheres.jpg"
   relative: false

---

## Professional Experience and Education

### Summary

**Amazon** | 2018 - present  
AWS Fargate Dataplane team - Building container orchestration infrastructure at scale using Go and Rust

**Impinj** | 2014 - 2018  
Infrastructure engineer building factory test systems and breaking monoliths into microservices with Docker

**Motorola** | 2007 - 2014  
Embedded software engineer writing mission-critical firmware for first responder radios

**IBM** | 2005 - 2006  
Co-op intern on ASIC design teams, writing test automation for chip validation

### Education

**Master's Degree in Electrical and Computer Engineering** - University of Florida (2011)  
**Bachelor's Degree in Computer Engineering** - Florida Atlantic University (2006)  
*Both earned while working full time*

---

## My Career Journey

This is the detailed story of my career so far. I've been lucky to work on systems that matter, solving problems that affect real people.

### IBM (2005-2006) | Co-op Engineer Internship, Rochester, MN

**My career in tech started with a firm handshake and a pitch I had to make work.**

It's 2005. I'm at a SHPE conference in Philadelphia, fresh back from a 15-month deployment in Iraq. I'm surrounded by hundreds of college students from big-name universities at a massive career fair - Georgia Tech kids in their bright yellow polos, students from MIT, Stanford. I'm just one more student from FAU, standing in a long line at the IBM booth.

Then I notice someone walking around chatting with people. I step out of line.

"Hello Sir, my name is Jose Villalta. I have a couple of things to tell you about me. I am a war veteran, I work full time to pay for school, I'm enrolled full time at FAU with a 3.8 GPA, my dad worked for IBM in the seventies, and I'd love to work for IBM now."

He looks at me, looks at my resume: "What do you want to work on, Software or Hardware?"

One word sealed my fate: "Hardware."

He handed me his business card and told me to email him what I just said. I did. After interviews in Dallas, I got an offer to join the ASIC Design group at IBM.

**What I learned:** Most internships are 12 weeks over the summer. Mine was six months full-time, on-site with the teams that design processors for mainframes, the Cell processor for Xbox and PlayStation, and more. I wrote Perl and Unix bash to parse requirement documents and generate test cases. I refactored factory tester scripts that validated silicon wafers in the fab. The domain was incredibly low-level - logic gate level, testing that AND gates behaved like AND gates.

When my six months ended, I asked if I could work remotely. They said yes. (This was 2005 - remote work wasn't common then.) I stayed for another year and a half, planning to join full-time and move to Rochester. But in Q4 2006, the department was cut in half. My job was moving overseas.

**The lesson:** Systems fail. Plans change. You adapt.

---

### Motorola (2007-2014) | Firmware Software Developer, Plantation, FL

**My first job out of college was writing code that first responders depend on when lives are on the line.**

I joined Motorola as part of a new hire wave to work on Project Mackinaw - the APX series radios. These are the walkie-talkies that police officers and firefighters use. When someone calls 911, the people who respond use radios running software I helped build.

I was assigned to the "low level" team working on the RF Deck. My code controlled and configured the RF hardware with precise timing to support the APCO P25 radio protocol. I worked on that product from initial design through launch, then stayed for new releases and features for seven years.

**What I learned:** Real-time operating systems. Memory and power constraints. The importance of reliability when failure means someone doesn't get backup. My team lead and mentor, Martin Elmore (now VP), gave me one lesson that shaped my entire approach to engineering: *"Catch your own bugs first. Don't let other people find your bugs."*

We wrote C++ in an unusual way - drawing UML diagrams that a tool (IBM Rational Rose) converted to code. Source control was machine-generated XML, not .h or .cpp files. Merges were nightmares. The tool was slow and crashed if the XML wasn't perfectly formatted.

I didn't know any better - this was my first job out of college. But I loved it. I made lifelong friends. I learned about radios, signal processing, wireless communication, and software engineering processes. I learned what "mission-critical" actually means.

**The lesson:** When your code powers radios that save lives, you build it right the first time.

---

### Impinj (2014-2018) | Seattle, WA

**I moved to Seattle to work for Impinj, a VC-funded startup that designed RFID chips. This is where I fell in love with distributed systems and containers.**

I was hired to build a new version of the factory tester software - a C++ application that validated silicon wafers in our fabs. After that project shipped, I joined the Factory Services team, building systems to ingest manufacturing data (test results, location, quantities, status) from factories around the globe to support engineering, operations, and business teams.

The system was a set of Ruby on Rails applications backed by MS SQL. This was my first time writing code for computers distributed across the globe that needed to coordinate and present accurate data. I was stepping from the embedded world into distributed infrastructure.

**Then I volunteered to be the "DevOps" person for my team, without really knowing what DevOps was.**

I immersed myself in containers. I remember attending a tech meetup at Google's Fremont campus where someone presented a new orchestration technology called "Kubernetes." I thought it was too complex for our use case. (I was wrong about that.) I led the effort to break up our Rails monolith so each service could be deployed separately in its own VM instead of one server hosting everything. I used Docker Swarm for orchestration, Chef and Ansible for infrastructure management.

**What I learned:** Working on problems nobody else had solved before. Building systems that coordinate across continents. The power of containers to simplify complex deployments. Impinj was a great place to work with smart people tackling hard technical problems.

**The lesson:** Sometimes the best career moves happen when you volunteer for something you don't fully understand yet.

---

### Amazon (2018-present) | Seattle, WA

**I've been in three different orgs over the past six years, finally landing where I wanted to be: building container infrastructure at scale.**

I joined EC2 first, writing automation to map new "bricks" (the beefy computers powering EC2) to their corresponding cells when first deployed in data centers. Six months in, I was recruited to the retail side.

I spent 2.5 years on the NARX team (North America Retail Expansion) operating as an "away team." We didn't own any specific tech - instead, we expanded the business to new marketplaces. Want to offer one-day shipping in Mexico? We'd learn all the systems involved, make the changes, and get the host team to approve them. I touched payments, accounting, search, catalog, delivery experience, and more. I worked with an awesome manager and awesome people.

**In 2021, I got the opportunity I'd been waiting for: to return to AWS and work in the container space.**

I joined the AWS Fargate Dataplane team. I maintain the Fargate Agent - the process that orchestrates containerized applications on behalf of millions of customers. I write Go and some Rust, working on system-level software at massive scale.

**In 2024, I led the networking design and implementation for ECS Managed Instances (Omakase).** This was critical infrastructure enabling customers to migrate from ECS on EC2 to Fargate's serverless model while maintaining flexibility for specialized compute needs (GPU, accelerated compute, specific CPU instruction sets). I designed support for multiple networking modes (awsvpc and host mode), implemented trunk/branch ENI architecture to achieve high task density beyond traditional ENI limits, and ensured backward compatibility so no customer gets left behind. The networking foundation I built removed a major barrier preventing ECS/EC2 customers from adopting Fargate's managed infrastructure model.

**What I love about this role:** I'm building the invisible infrastructure that powers visible applications. Healthcare systems, financial services, disaster relief coordination, educational platforms - they all run on infrastructure I help maintain. The decisions I make about reliability, performance, and efficiency ripple out to affect millions of end users who never see the container orchestration layer.

This is where my whole career has been leading: embedded systems taught me how hardware works, Motorola taught me what mission-critical means, Impinj taught me distributed systems and containers, retail taught me scale and complexity. Now I'm applying all of it to build infrastructure that has to work, every time, at AWS scale.

**The lesson:** The best technology is invisible until you need it - then it's absolutely dependable. That's what I build.

---

## What's Next

I'm focused on deepening my expertise in container orchestration, becoming a technical leader who shapes not just how we build infrastructure, but why we build it the way we do. I want to influence the strategic direction of infrastructure that serves humanity at scale - reliable, sustainable, and built for everyone.