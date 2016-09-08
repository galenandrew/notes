# Thursday Sessions
2016-09-07

---

# Keynote: From Failure to Flawless: Application Delivery Today

## NGINX
180 Million Domains
53% of top 10k websites
100 people

---

# Keynote: NGINX: Past, Present, and Future
@owengarrett Head of Product, NGINX

## What's new?
- Dynamic Modules
- UDP Load Balancing
- [NGINX+] OAuth authentication _(enables rate limiting per individual user vs IP, etc)_
- [NGINX+] Service discovery integration
- ModSecurity

## What's next?
- **nginScript**: Extend NGINX functionality using directives and expressions written in JavaScript
- **NGINX Amplify**

---

# Data-Driven Postmortems

- Blameless Postmortems http://bit.ly/etsy-blameless

## Metrics
- Work Metrics
	- throughput
	- success (%)
	- error (%)
	- performance
- Resource Metrics
	- utilization
	- saturation
	- error
	- availability
- Events
	- code changes
	- alerts
	- scaling events
	- etc (deploys, commits, builds, updates, etc)

Metrics should be…
- well-understood
- granular
- tagged by scope
- long-lived

[Joyent Postmortem](http://bit.ly/joyent-post)


- John Allspaw [The Infinite Hows](http://bit.ly/infinite-hows)
- ["Blameless" Postmortems don't work](http://bit.ly/blameless-dont-work)

---

# Microservices & API Gateways
Marco Palladino

Kong is built on top of OpenResty
