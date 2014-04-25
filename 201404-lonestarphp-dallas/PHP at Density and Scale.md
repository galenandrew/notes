# PHP at Density and Scale
@speaker David Strauss

## Overview
Mixing performance, configurability, density, and security at scale has, historically, been hard with PHP. Early approaches have involved CGIs, suhosin, or multiple Apache instances. Then came PHP-FPM. At Pantheon, we've taken PHP-FPM, integrated it with cgroups, namespaces, and systemd socket activation. We use it to deliver all of our goals at unheard-of densities: thousands and thousands of isolated pools per box.

## Topics
**Broadly Defining Security**
Your Data...
- is accessible to the right people (access)
- isn't to anyone else (access)
- is usable (quality of service)

**Performance**
- Socket activation
- automount/autofs
- cgroups
- Customer Experience Monitor
- Migration

**Security**
- Users
- Namespaces
- Defense in depth
- non-disruptive fixes

## Challenge: PHP-FPM Overhead
Using a full php-fpm instance per stack
- isolated opcode cache space
- defines-in-depth against php issues
- low-impact reconfiguration

**Idle PHP-FOMs take ~0.5% of a core each**

## Sockets
If you want a service available, the daemon has to be running...

**Socket Activation**
Open a socket, put a listener (EPOLL) on it - start things on demand

- systems squats on all listeners
	- looks for incoming traffic with EPOLL
	- Starts the services

## Challenge: Resource Availability
- per-site load isn't predictable
- different sites compete for resources

**cgroups**
- many options (pantheon uses CPUShares and BlockIOWeight)


## Defense in Depth

### Application
- Drupal
### Runtime
- Nginx, PHP-FPM, FuseDAV
### Container: binding cert
- linux user, namespaces
### Container host: endpoint cert
- only trusted for the containers assigned
### Platform: root assigned

