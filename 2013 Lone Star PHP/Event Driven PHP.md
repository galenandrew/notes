# Event driven applications in PHP
@author Bob Majdak
@date 2013-06-28
@url joind.in/8700

## Typical PHP App
- Page Hit
- - Init [Framework]
- - Configure [Framework]
- - Setup [Framework]
- - Ready
- - - Input (Handle GET/POST, decide what to do)
- - - Main (do stuff)
- - - Output (toss it out to the browser, themed)
- Shutdown [Framework]

## Events…
- …are things that happen
- …can be emitted, signaled, thrown, set, 
- …must be handled, listened for, watched for, caught, received

## Event System Types
**Loosely Synch**
- basis of a solid system

**Asynchronous**
- basis of queue system


## ReactPHP
- NodeJS for PHP
- @url speakerdeck.com/igorw/react-phpbnl13

**Uses**
- PHP Stream (stream_select)
- LibEvent
- LibEV

## Metaphor
- Mason Jar (Event Loop)
- Jar Lid (Server)

## Demo
- Baseball Game
- Pitcher/Catcher
- 