# Modern HTTP Architecture
@author Travis Swicegood, @tswicegood
@date 2013-06-28
@url tswicegood.github.io/modern-http-architecture (using reveal.js)
@feedback joind.in/8727

## About
- Where we're going…not where we're at
- web/http
- this is a theory talk

## Traditional
- "One Server", Req/Resp model (mod_php does a lot of the grunt work)
- "Server Pool", vertical/horizontal scaling

### Benefits
- Easy to scale

### Downsides
- Efficient scaling (one piece causes entire app to scale)
- Resiliency (one failure causes entire failure)

## Future
> Small, simple, working together
- UNIX philosophy of programming
> Write *programs* that do one thing and do it well. Write *programs* to work together. Write *programs* to handle *text streams*, because that is a universal interface.

> Write *web services* that do one thing and do it well. Write *web services* to work together. Write *web services* to handle **JSON data**, because that is a universal interface.

### Examples
- ORCA - Obama campaign
- [Nodeload GitHub](https://github.com/blog/678-meet-nodeload-the-new-download-server)

## Implementation Workflow
- Not as easy
- Requires more planning (Software Architect plans, Jr Developer executes)
- Refactoring isn't trivial (if you change your API, you have to change every service that uses it)

### HaaS - HTML as a Service
- Just like any other service
- Serves same function as iOS App

## Resources
### Software
**Nginx**
- Everything can be routable
- - Use same domain, but routes separately
**Varnish**
- makes web requests really fast

### Further Reading
**12 Factor**

## Developing in SOA
**Virtual Machines**
- Vagrant (Automates creation of VMs)