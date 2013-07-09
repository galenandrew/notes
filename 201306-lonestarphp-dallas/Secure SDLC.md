# An Introduction to the Secure Software Development Lifecycle
@date 2013-06-28
@author Neal Anders, neal-anders.com, @nanderoo (github)
@url joind.in/8682

## Secure Software
- resilience
- dependable
- trustworthy

> "…the level of confidence that software is free from vulnerabilities, either intentionally designed into the software or accidentally inserted at anytime……

## Secure Software Development
SSD vs SDL
- more than one flavor
- different approaches/frameworks
- OWASP
- SANS/NIST/IETF
- BITS

*SSD Process/Steps*
Initiate > Develop > Implement > Operate > *Dispose*

## Requirements & Design
Difference with Secure Requirements
- Front-loading
- Thinking about things other than *features*
- Requirements & Risk measurement
- Design is not eye-candy + pixel pushing
- Sometimes at the expense of usability

Design Aspects of SS
- Redundancy
- Stability
- Graceful Fall-over/Failure (Graceful Degradation)
- …and recovery!
- Data integrity
- Information Assurance
- Threat Modeling

## STRIDE
- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

**Spoofing** - Session Hijacking
- Monitoring Network Traffic
- Examining Headers/Cookies/Session IDs
- Employ SSL
- Multi-factor authentications

**Fuzzing**
- Limit inputs (e.g. flooding max-length)
- SQL injection (potentially)

**Data Access/Theft**
- Cloistering DB and application servers

**Variable Sanitation**
- Prevent wildcards, etc (?customer_id=*)

**Auto Refresh / Throttle / Firewall / DoS**
- Time limits between updates (e.g. wait 5 minutes before updating profile picture, etc)

**Privilege Elevation**
- Upload media that executes imagemagik, etc and opens up a command prompt

## Development & Testing
What's different
- Requires you to think about what may not be in the specs
- Error handling becomes the first step/second nature
- Testing becomes as much about making tests pass with expected behavior and pass with failed expected behavior
- More than 1 time unit tests

## Least Privilege
> The concept that…for a given task to be completed, it should be accomplished in the shortest amount of time, with the least amount of resources and permissions

### Flexible vs Strict Permissions
- We often want to create a b beautiful machine
- Often develop complex features (easy user permission management, etc)  that aren't specific requirements


## Misc
- "Bike-shed"ing
- Red Team
- "Beach Certify" your app (e.g.…from your chair on the beach using your phone)