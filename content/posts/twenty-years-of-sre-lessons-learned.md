---
title: "Article Review: Lessons Learned from Twenty Years of Site Reliability Engineering"
date: 2023-10-31T08:29:26-07:00
draft: false
---

### Article: Lessons Learned from Twenty Years of Site Reliability Engineering

[Link to article](https://sre.google/resources/practices-and-processes/twenty-years-of-sre-lessons-learned/)

The site realibility team at Google put together a summary of the lessons they have learned over the years. I am glad they decided to share. The best way to learn is by trial and error. Want your product or service to be better? Launch it, monitor it, and learn from the mistakes. It nice to learn from others, but there is no substitue to first hand experience.  This is the list they came up with:

- 1. The riskiness of a mitigation should scale with the severity of the outage
- 2. Recovery mechanism should be fully tested before an emergency
- 3. Canary all changes
- 4. Have a "Big Red Button"
- 5. Unit tests alone are not enough - integration testing is also needed
- 6. COMMUNICATION CHANNELS! AND BACKUP CHANNELS!! AND BACKUPS FOR THOSE BACKUP CHANNELS!!!
- 7. Intentionally degrade performance modes
- 8. Test for Disaster resilience
- 9. Automate your mitigations
- 10. Reduce the time between rollouts, to decrease the likelihood of the rollout going wrong
- 11. A single global hardware version is a single point of failure

My team has learned these lessons the hard way. I must say we do a good job with number 5. Our end-to-end tests are more meaninful than the unit tets. Not saying the unit tests have no value, we would be in a lot pain if we didn't have unit tests. The end-to-end integration tests cover a lot of functionality you can't test with UTs. Number 6 is kinda funny, I remember when we had a ticketing system outage so we were "flying blind" for a little while, I don't know what was the cause or what happened, I just remember heearing about it and thinking, oh wow. 

Number 10 is a struggle, we've got a complex rollout process with many, many, moving parts. We constantly roll deployments back to keep quality high but that translates into more time between deployments. That also sucks, because the less often you do it, the more painful it becomes. 

### Conclusion

I am glad I came accross this article. I am going to take a look at the [Canary Paper](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/24017e52c907294589604a29a86f158828eda078.pdf) they used and see if I can convince my org to rely on it more. I mean, we do have canaries, but are we using them enough and effectively? I think we can always do better. 

-JV

