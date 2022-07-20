---
title: "Paper every day. Day Four: Harvest, Yield, and Scalable Tolerant Systems"
date: 2022-07-20T06:28:24-07:00
Author: Jose Villalta
---

[Link to paper](https://s3.amazonaws.com/systemsandpapers/papers/FOX_Brewer_99-Harvest_Yield_and_Scalable_Tolerant_Systems.pdf)

Today's paper comes thanks to [Will Larson](https://lethain.com/) this is a recommended paper in his book [Elegant Puzzle](https://www.amazon.com/dp/B07QYCHJ7V/)

This paper builds on the concepts from the the [CAP Theorem](https://en.wikipedia.org/wiki/CAP_theorem) which essentially says that when it comes to distributed systems you can only have 2 out of these 3 qualities:

- Consistency

- Avalaibility

- Partition Tolerance

Then it introduces two concepts **harvest** and **yield** which is interesting because it's not something you usually hear in distributed systems (this is a paper from the '90s) and yet I think it's import to know and to think in these terms. 

### Harvest and Yield principles

Yield is the probability of completing a request. It's what you would typically measure in "nines" as in "four-nines availability" 

Harvest measures the fraction of the data in the response, and it measures the completeness in the response. 

There is usually a tradeoff between returning an error versus returning imcomplete answer in the presence of system faults. This paper makes the arguement that we should aim to trade harvest for yield in applications that can tolerate some degradation in the harvest. Will Larson liked this paper because it introduces some rigor and predictability to distributed system error response. If you are going to fail, it's good to know and define how your system will degrade as opposed to letting it degrade in undefined or unpredictable ways. Sometimes it's better to crash early than to limp along say, ATM withdrawals for example. Other times it's okay to have an incomplete answer, like in when doing internet searches. 

The paper's focus is on techniques for improving availability. They mention application decomposition and orthogonal mechanims. 

### Application decomposition

Break up your system so that independent failures allow graceful degradation. 

### Orthogonal mechanism

If you can break up the components in a way that they do not directly depend or interact with each other. (Think layers above or bellow) If we break up the functionality in such a way that a failure in one system has zero effect on another system then you can have more robustness are better isolation. 


### Conclusion

The concept of breaking up the system into independent compoents is not a new thing, but I liked the idea of thinking in yield and harvest, if the application can tolerate harvest degradation, then can keep the yield high. 





