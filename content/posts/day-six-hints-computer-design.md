---
title: "Paper every day. Day Six: Hints for Computer Design"
date: 2022-07-22T08:13:55-07:00
Author: Jose Villalta
---

[Link to Paper](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/acrobat-17.pdf)

This paper was published originally in 1983 by the legendary folks from the Xerox Palo Alto Research Center. 
The hints and tips should sound familiar but it's interesting to notice the **layer** the author is talking about, these guys were designing at very low level. 
The fact that the same rules apply now it's remarkable. It turns out breaking up a system into the right abstraction with a good interface it's rather hard. 

The author breaks up the hints into three main categories:

- Functionality
- Speed
- Fault Tolerance

The need for speed must have been critical back in the 80's. It still important today, I remember reading somewhere that an increase in latency of 200ms for load time in a retail page results in something crazy like 10% less orders. That translates to millions when you operate at large scale. 


The paper reads like an intimate blog posts instead of an academic article. The guys are Palo Alto must have been very comfortable to write in an informal manner, which I don't mind at all. 

This is a Summary of their findings:

### Functionality

- Keep it simple. Do one thing at the time, and do it well. Get it right and get it fast. 
- Don't hide power
- Hide implementation details
- Leave it to the client. (don't make assumptions for the user and let her compose the functionality she wants from your building blocks)
- Continuity: Keep basic interfaces stable. 
- Plan to throw one away
- Handle normal and worst cases separately

### Speed

- Make the most common case fast. Don't make the average user pay for the worst case. 
- Split resources
- Use static analysis
- Cache answers
- Use hints (?) to speed up normal execution. (that was interesting)
- When in doubt use brute force
- Compute in background
- Use batch processing if possible
- Safety first
- Shed load (so applicable today in large distributed services)

### Fault Tolerance

- Test End-to-End
- Log updates (Today it would be, log all state changes)
- Make actions atomic or restartable (+1)


### Conclusion

This paper is a classic and a must read for all of us striving to build complex systems. The examples provided after each hint it's what makes the paper a good read, they are fascinating that the words feel familiar but the systems the author mentions are still around today (Unix and its utilities) if not the same implementation, the same desing and architecture are still with us and still kicking. It feels like those things NEVER fail, never have bugs and were designed by perfect engineers, but that's obviously not the case. The author make the case that good engineers can achieve more with less, more performance with less powerful hardware, but my view is the opposite, engineers are people and will make mistakes and our systems have to be able to tolerate failures. 

