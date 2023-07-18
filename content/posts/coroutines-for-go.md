---
title: "Coroutines for Go"
date: 2023-07-18T06:51:45-07:00
Author: Jose Villalta
---

### Go 
Russ Cox put out an [article](https://research.swtch.com/coro) yesteday about adding the abilities to run coroutines in go. Today I learned the difference 
between a [goroutine](https://go.dev/tour/concurrency/1) and a [coroutine](https://en.wikipedia.org/wiki/Coroutine). Coroutine is a concurrency pattern in which only one runs at a time. Say we have coroutine A and B. B waits while A runs then A yields to B and A waits while B runs. It turns out this is useful in a few scenarios.

Should we add it to a Go library? Yes. Should it become part of the language? I'm not sure we need to, but we'll see. 

[Link to Russ Cox's Article](https://research.swtch.com/coro)

-JV