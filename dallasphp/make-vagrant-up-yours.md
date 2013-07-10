# Make $ vagrant up yours
@speaker Juan Treminio, @juantreminio
@date 2013-07-09

## Misc
- Vagrant is a command line tool to manage virtual machines
- Puppet is a command line tool to install software and configure virtual machines
- PuPHPet …

## Why use virtual machines?
- Some tools are difficult to install (e.g. Memcached, Mongo, misc packages, configs, etc)
- Some programs on your daily OS may interfere (e.g. Skype uses port 80, firewalls, etc)
- *It (or doesn't) works on my machine!* is no longer an issue
- It's very easy and fast to on-boarding new developers and get environments setup
- Replication or mirroring of production environments

NOTE: Manually managing a virtual machine is error prone and not easily replaceable.

## Enter Vagrant…
*Handles virtual machine creation*

### How it works
- Works off a `vagrantfile` (*a plain text config file that defines the virtual box's configuration*)
- Requires its own IP address (LAN IP, e.g. 192.168.56.101)
- Can define "synced" folders, e.g. mirrors/maps local folders to a place inside the virtual machine (POWERFUL FEATURE)

### Benefits
- Vagrant makes virtual machines **disposable** and replicable
- Creates a new VM from the ground up very quickly
- Provides ability to easily replicate distributed environments locally (full local SOA!)

### Kicking it off...
- `cd` into the directory where the vagrantfile exists and run `vagrant up`
- `vagrant ssh` allows you to *tunnel* into your VM without the need of passwords, SSH Keys, etc

## Puppet
*The tool used to install software and configure the virtual machine*

### How Puppet Works
- Uses DSL (domain specific language), i.e. its own language
- `./default.pp` defines puppet configuration
Basic File/Folder Structure
```
Vagrantfile
manifests/default.pp
```

### Modules
- Puppet modules are similar to PHP libraries
- Small packages of code that do things
Example:
```
apache::vhost { 'puphpet':
	server_name   => 'puphpet.dev',
	serveraliases => ['www.puphpet.dev'],
	docroot       => '/var/www/puphpet.dev/web',
	port          => '80',
	priority      => '1'
}
```

### Downsides
- Puppet is…finicky
- Doesn't execute sequentially (will sometimes run commands in random order), but rather cares about dependencies
- Uses its own language
- Sometimes errors are cryptic (difficult to understand/debug)

### Sample Puppet Manifest
…

### Misc
- **Example 42**: A guy that creates custom puppet modules/classes

## PuPHPet
*A GUI tool that creates custom Puppet configuration manifests*

### What is does?
- Allows developers to select options and download a ready-baked Puppet manifest

### Goals
- One-stop shop for quickly and easily getting a development environment up and running
- Easily customize your environment to fit your needs
- Provide production-ready VMs
- Quick-start configurations