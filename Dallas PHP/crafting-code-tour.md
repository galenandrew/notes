# Crafting Code Tour
@date 2014-07-08

## Sponsors
- [Code Climate](https://codeclimate.com)
    - AWESOME!!

# Your code sucks! Five tools for evaluating the quality of your code
@speaker Brandon Savage

### Overview
You know you want to write great code, but how do you know what great code looks like? Using these tools, you'll be able to figure out exactly what areas of your application are great, and which could use the most improvement. Plus, learn how to apply these tools on a daily basis in your development, automatically!

------------------

# It Was Like That When I Got Here: Steps Toward Modernizing a Legacy Codebase
@speaker Paul Jones
@video https://vimeo.com/47849625

## Overview
The codebase at work is absolutely terrible. It's a mess of spaghetti that has been around for years and is and completely untestable. Any time you fix a bug over here, a new bug appears over there. In this talk, Paul explains how the code got to be so bad, and gives practical steps on how you can start paying off the technical debt you inherited with your legacy application, all while keeping the system running the whole time.

## Book Recommendations
- [Refactoring: Improving the Design of Existing Code](http://www.amazon.com/gp/product/0201485672)
- [The Mythical Man-month](http://www.amazon.com/The-Mythical-Man-Month-Engineering-Anniversary/dp/0201835959)
- [Clean Code: A Handbook of Agile Software Craftsmanship](http://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [Modernizing Legacy Applications in PHP](https://leanpub.com/mlaphp/c/craftingcode2014)

## Parking Lot
- [Spiral Model](http://en.wikipedia.org/wiki/Spiral_model)
- [Characterization Tests](http://en.wikipedia.org/wiki/Characterization_test)
    - Contrary to Unit Tests which measure/test the internals, Characterization Tests

## Quotes
--
> Beware: Things that go away by themselves, come back by themselves.

--
> "There are no solutions; there are only trade-offs" - Thomas Sowell



## About Paul Jones
- 8 years USAF Intelligence
- Aura project (open source project)
- PHP-FIG (PSR-1, PSR-2, PSR-4)
- Action-Domain-Responder
    - [Blog article](http://paul-m-jones.com/archives/6006)
    - [GitHub](https://github.com/pmjones/mvc-refinement)

## Part 1
_Spaghetti Code_

_Why/How did it get this bad?!_
- The Great|Aweful thing about PHP - EVERYONE CAN DO IT!
- Original developer probably didn't know better
- Subsequent developers worked with what was there
- "We can fix it later…"
- …until later becomes now

### Technical Debt
> All of the things that you should have done, that you didn't do.
> Can't just be fixed in a single place, but rather a coordinated change across the entire codebase.

#### Paying Off Technical Debt
- A lot like paying off financial debt
- Got the stuff first (earlier), but have to pay for it eventually
- Must pay off technical debt not of our own choosing
- Suffer as things are, or suffer through change

> Choose the kind of suffering you want to endure (work in bad code vs extra work to improve things)

##### Declare Bankruptcy
- Rewrite from scratch!!
- Expend effort while not earning revenue
- Old devs on new project? New devs on old project?
- Takes longer than you think (take it, double it, convert to next higher unit: 4 wk = 8 month)
- End up with different bad architecture

##### Incremental Approach
- Equivalent of increased monthly payments
- small changes across entire codebase
-

### Incremental Goals
- Keep the application running
- Consolidate classes for autoloading (PSR-0 recommended over PSR-4)
- Convert globals to inject dependencies
- After each change: TEST, commit, push, QA

### Dependency Injection
- Class reaches out to get dependencies
