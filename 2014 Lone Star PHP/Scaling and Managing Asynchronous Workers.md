# Scaling & Managing Asynchronous Workers (and staying sane!)
@speaker Justin Caramony @justincaramony
@deck joind.in/10809

## Overview
There comes a point in time with a website when eventually need to do something in the background. There are always cron jobs, but eventually those either don’t scale well, or are not responsive enough. Learn about how to help your website efficiently scale by using workers. We’ll touch briefly the fundamental theory behind workers and how to easily implement them. We’ll learn about several different technologies to help manage workers such as Gearman, Supervisord, Redis, and others. We’ll show a live demo of PHP workers performing tasks and you’ll leave with sound understanding of how to implement workers in your own application.

## Outline
- Theory Behind Workers
- ...


## Theory
- have a job
- put it in a queue
- worker takes the job
- worker does the job

### Managing workers can be complex
**Long running**
- hours vs milliseconds
- php isn't written to be long running
- most connections have timeouts

**Keep them running**
- what happens when a worker dies
- restart workers?

**Monitoring**
- what is my worker doing?
- is it frozen/hung?
- what happened to the job?

**Potentially Dangerous**
- fills disk with temp files
- ..

## Best Practices for writing workers
>> SIMPLICITY!! (avoid complexity)

### Use the right/better tools
- Cron vs workers

**Better Queues**
- Beanstalkd (speaker recommended)
- RabbitMQ
- Redis
- Gearman
- Amazon SQS, IronMQ

**Poor Queue**
- Rel DB (MySQL, PostgreSQL)
- Doc Store (Mongo, Couch)
- Flat files

**Beanstakd**
- very fast (in mem by default)
- dynamic queue which they call "tubes"
- Bury jobs that have an error, kick them back into queue when ready
- job re-enter queue if not finished by timeout
- can put jobs in via a delay

### Example Stack
- PHP
- Beanstalkd
- Redis
- Pheanstalk (php lib to talk to Beanstalkd)
- Predis (lib to talk to Redis)

### Queue lifecycle
- Put
- Reserve
- Delete
- _Delayed_
- _Ready_
- _Buried_
- _Failed_

### Job Data
- Use JSON for storing job data
- Use a common structure for all jobs (`obj.job`, `obj.data`, `obj.success`, `obj.failure`)

### Naming Conventions
- create queues for each type of job (not one queue for all jobs)
- use priorities sparingly

**Examples**
- email.priority
- email.regular
- email.bulk

### Options for Queueing in BS
- Data
- Priority
- Delay
- TTY (time to run?)

### Use Better Tools - Workers
**Better Workers**
- run from command line
- bootstrapped and auto-loaded
- blocked listening to queue
- takes CLI args
- Can run multiple on same server

**Poor Workers**
- run from cron script
- one off scripts

#### Run From Command Line
**Benefits**
- no complexity of web server (not designed for long running scripts/connections)
...


## Setup
### PHP Timeout
- `set_time_limit(0)` disable limit

### Setting Up Worker
- Assign two values to each worker
	- Worker ID
	- Instance Hash

### Creating Connections
- connection dying/timing out is #1 cause for errors in workers
- Close connections before each job
- Close & Re-open connections for infrequent or long running jobs

### Retrieving job
**Old Way**
- infinite loop w/ `sleep(5)`...on periodically forever (if not immediately available, closes the connection then waits to reconnect)

**New Way**
- Blocking...always on (establishes the connection and holds it open for period of time then returns false, e.g. closes then immediately reopens the connection)

## Running the job
...

## Logging
- PSR-3
- Monolog (keeps it simple https://github.com/seldaek/monolog)

### Reporting Status
- insight into what workers are doing is critical
- _Heartbeat_

### Shutdown/Restart
- don't `exit()` or `die()`
- `$worker->run = false;` when worker needs to stop
- `$worker->run = true;` when worker needs to run

### Controlling Workers - System Queue
- create queue for each worker based off ID (send jobs for indv workers, e.g. wait, shutdown, etc)

## Keeping the Workers Running

**Supervisor**
- Linux based tool for keeping processes running
...

### Monitoring Tools
- ... / Graphite
- Nagios - Alerts