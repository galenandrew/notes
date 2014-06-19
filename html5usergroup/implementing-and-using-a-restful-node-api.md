# Implementing and Using a RESTful Node API (Part 2)
@speaker Eric Sowell @mallioch eric.sowell@gmail.com
@date 2014-06-18

## Overview
Continuation of series on Node and RESTful APIs.

## REST

> The Web is RESTful. A RESTful API is one that follows the architecture of the web.

**What REST is NOT defined as…**
- Nice URLs
- Using JSON
- Not SOAP

**Resources and Representations**
- When you navigate to a URL on the web, you are receiving a "representation" (or copy) of the actual resource.

**URLs/URIs**
- The URL/URL is the most important part of the request

**Status Codes**
- More predictable because the body doesn't have to be parsed/interpreted

**Consistency**
- in URLs
- in Resource Shape
- in the use of HTTP status codes
- in the use of HTTP verbs
> Consistency means that the code to interact with an API can be minimized


**HATEOAS / Hyperlinking**
> HATEOAS - Hypermedia As The Engine Of Application State

- *How to handle hyperlinks with versioning?*
    - Model vs Database
    - Controller modifies returned model based on actions/permissions/version/etc
- Return the URLs for the resources requested

> Request without a response, is truly a sad moment


## Misc
- `body-parser` - NPM module, this only handles urlencoded and json bodies.
- Resify -
- Charles (HTTP Proxy) - application to proxy all http requests
- [httpstatuscod.es](http://httpstatuscod.es) - great list of HTTP status codes and their meanings
- [Seven Databases in Seven Weeks](http://pragprog.com/book/rwdata/seven-databases-in-seven-weeks)
- [Seven Languages in Seven Weeks](http://pragprog.com/book/btlang/seven-languages-in-seven-weeks)
- UnderscoreJS
- Roy Thomas Fielding - describes concepts of REST in a dissertation on
[Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/fielding_dissertation.pdf)
- REST API Design Handbook
- RESTful Web APIs
- REST in Practice

## Questions
- How to handle versioning in HATEOAS?
    - Answer: Restify handles this nicely with ACCEPT-VERSION headers via [Versioned Routes](http://mcavage.me/node-restify/#Routing)
