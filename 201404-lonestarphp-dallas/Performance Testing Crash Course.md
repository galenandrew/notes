# Performance Testing Crash Course
@speaker dustin whittle
@deck speakerdeck.com/dustinwhittle

_...joined late due to registration_

## Overview
The performance of your application affects your business more than you might think. Top engineering organizations think of performance not as a nice-to-have, but as a crucial feature of their product. Those organizations understand that performance has a direct impact on user experience and, ultimately, their bottom line. Unfortunately, most engineering teams do not regularly test the performance and scalability of their infrastructure. Dustin Whittle shares the latest performance testing tools and insights into why your team should add performance testing to an agile development process. Learn how to evaluate performance and scalability with MultiMechanize, Bees with Machine Guns, and Google PageSpeed. Take back an understanding of how to automate performance testing and evaluate the impact it has on performance and your business.

## Tools
- Bees with Machine Guns (https://github.com/newsapps/beeswithmachineguns)
- Google Page Speed Optimizer
- WBench
- Sensu (Open Source Monitoring)

- statsd (pull stats from anything), Graphite (graph), graphing (awesome ui layered on top)
- boomerang

- webpagetest.org

- **sitespeed.io** (client side library that does performance testing. can integrate with Jenkins...cool graph)

## Paid Tools
- blitz.io
- apica (real browsers)
- BlazeMeter

## Testing for Failures
- NetFlix Simian Army + Chaos Monkey
What happens if you lose a caching layer?
- What happens if dependencies slow down?

## Best Practices
- Capacity plan/load test the server side
- Optimize and performance test the client side
- understand your starting point
- instrument everything
- Measure the difference of everything
- automate performance testing in your build and deployment process
- understand how failures impact performance