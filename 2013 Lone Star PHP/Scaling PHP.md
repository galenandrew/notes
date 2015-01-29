# Scaling PHP in the Real World
@author Dustin Whittle
@date 2013-06-28
@url speakerdeck.com/dustinwhittle

## Why does performance matter?
- Conversions!
- Affects the bottom line

## PHP is…
- slower than other languages
- has inconsistencies
- phpsadness.com

## How to run PHP
- NginX + PHP-FPM
- Opcode Cache…USE IT!!
- - APC
- - Zend Optimizer
- - - Default in PHP 5.5
- Autoloading…USE IT

## Scaling beyond 1 server
Issues - Sessions
- BAD - Default is store sessions via write to disk 
- GOOD - store in DB
- Better - Store in DB w/ Cache
- BEST - limit session size and store in encrypted cookie

## Cache
### Data/In-memory
- Memcached
- Redis
- - More advanced data storage structure (e.g. sets)

### DB / ORM
- Highly recommends Doctrine (DB ORM + Caching)

### Why?
- any data that is expensive to generate/query
Examples
- REST APIs

## Queue
Reason - Do blocking work in the background

### Resque
- very simple and easy to use

## HTTP Caching
- RTFM
- Expires or Invalidation

### Expires
- CSS/JS, etc
- Browser Checks date then either serves from Cache or server

### Last Modified (hits server)
- Browser asks server
- Server checks last modified then either serves from cache or renders page (middleware b/w browser and server)

## If-None-Match (hits server)
- E-Tag (self-defined key identifying page at a specific state)
- ESI - Edge Side Includes (single page with several dynamic components)
- - Example: Home page with top headlines, most recent comments, etc

### Varnish
- GREAT/EASY!!
- Sits in front of app server

### Benefit
- Alleviates load on application server
- Security (e.g. DoS) - Caching can handle > 10k req/s and prevent hits to app server

## Optimize your Framework
- Turn off features you're not using (e.g. internationalization, security)
- Leverage framework based caching first

## Sharding
- taking a large problem and making it into manageable pieces …

### Data Sharding
- Read sharing is easy…write sharing is a bitch
- Chose good shard keys (hash data, then use the hash as a key…vs ids, etc)

## Ways to Scale
- SOA - Service Oriented Architecture
> Big Apps create back-end in java/Scala/etc and front-end in PHP or pure javascript (AngularJS, Ember)
> Companies of great scale typically move away from PHP
- Learn how to profile PHP for performance issues
- - XDEBUG + WEBGRIND
- - XHPROF
- Don't forget to scale the client side! (e.g. Google PageSpeed)

> **Scalability** is about the entire **architecture**, not some minor code optimizations