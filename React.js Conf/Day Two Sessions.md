# Day Two Sessions

------------------------------------

# React Native
- Chris Chedeau

## Three Pillars
- Touch Handling
- Native Components
- Style & Layout

## Native Components
> React Native runs your JavaScript code inside Chrome's V8

React Native does not transcode/transpile your JS into Objective-C or C

## Style
- CSS has problems (too many to list)…solution is *CSS in JS*
- Style declaration is JSON/JS Obj based
- Styles are applied via inline styles

## Layout
- …just boxes on the screen
- Only cares about 4 values – Left, Top, Width, Height
- iOS has auto-layout vs having to manually calculate/define the layout values
- Auto-layout is a constraints solver
- CSS Box Model is better, but still has challenges (eg. vertical centering, multi column, etc)

**Flexbox to the rescue!!!**

- Flexbox requires the browser, but React Native is just JS and Native Components

> We need to reimplement Flexbox!

- React Native converts flexbox styles into Left, Top, Width, Height

- React Native - Reloads native app within seconds of change, uses Flexbox, CSS w/ JS Objects, ES6, supports NPM Modules
- "Red Screen of Death" Error reporting
## Demo
_…absolutely amazing!!…_

------------------------------------

# React and Web Components
- Andrew Rota @andrewrota
- Works at Wayfair

## Web Components
- Technologies that make up Web Components
    - Custom Elements
    - Shadow DOM
    - HTML Imports
    - HTML Templates

### Custom Elements
- Allow you to create your own custom elements
- Register it with the browser
- MUST CONTAIN A DASH (per the spec to avoid element name conflicts)

### Shadow DOM
- Allows you to fully encapsulate the styles and elements of your Web Components

> Web Components are portable, because their API is the web platform itself

## React + Web Components
- At first, Web Components weren't compatible in React/JSX because it wouldn't know if it was a custom React Component vs a DOM Node
- `0.13-rc1` introduced a convention that all lowercase or elements with a dash would be treated as HTML that opened the door for using custom Web Components

## Best Practices for Web Components for -React.js- Anything

### Web Components Should Be…
1. Small
    - If it doesn't make sense to eventually be a stand alone DOM element, it shouldn't be a web component
    - Good Idea `<my-button></my-button>`
    - Bad Idea `<my-application></my-application>`
2. Extremely Encapsulated
    - *Not All Web Components Are Created Equal!!*
    - Attributes `<paper-toast text="Hello, World">`
    - Methods `getDOMNode().toggle()`
    - Events `<paper-toast onclick={this.myCustomEventHandler}>`
3. As Stateless as possible
    - "Try to keep as many of your components as possible stateless." - React.js Documentation (also applies to Web Components)
4. Performant
    - "Your application is only as fast as it's slowest component"

> Web Components should seem no different than native DOM elements


## React w/in Web Components?
- Interesting concept, but introduces multiple challenges
- Goes against the core concepts of Web Components (eg coupling a framework dependency inside your Web Component…it is no longer small)

> If you think to yourself, "I wish I had React to manage functionality within my component", it's probably too _big_ to be a Web Component

------------------------------------

# Immutable Data & React
- Lee Byron @leeb

## Persistent Immutable Data Structures
- Immutable: Once you create one, you can never change it
- Persistant: Does not mutate, remains unchanged

_example of pushing to a list…clone original, add to, return new_

- They work because of structural sharing

## Interface vs Implementation
- DAG: Directed Acyclic Graph

### Trie (reTrieve)
- Index Trie
    - bit shifting, hops, and look ups…eg `list.get(141)`
- Hash Trie
    -

> Implementations are *Tries* and Interfaces are *Lists* and *Maps*

## People to Research
- J.R. Lickliter (sp?)
- Alan Kay
- Phil Bagwell
- Rich Hickey

## Why, What problems does it solve?
- Multi-threaded…

**`Object.observe` (will be in ES7)**

_Memoization_

> Flux store is an identity, …

------------------------------------

# Beyond the DOM: How Netflix plans to enhance your television experience
- Jafar Husain

# 3 things you don't know about Netflix
1. Netflix loves JS! (wants to be wherever you are)
2. Super secret TV Platform – Gibbon vs Webkit (3 UIs – Mobile, Web, TV)
3. Love React.js because of Performance and Simplicity

------------------------------------

# Scalable Data Visualization
- Zach Nation @reverius42 @znation
- Sample / Demo https://github.com/znation/scalable-data-visualization

> Humans are really good at identifying visual patterns

## GraphLab Create (Dato)
- https://dato.com/products/create/docs/graphlab.canvas.html

## Challenges with Visualizing Raw Data
- Condensing data to a smaller set of visual elements
- maintaining a high level of …

## Data Visualization Pipeline
- D3.js
- React.js

## Principles
- Compute close to the data

## "Flux" on the server
- replaced Dispatcher with XHR/WebSocket
- replaced Store with Statefull Server

## Scalable Aggregation
- Binning
- Constant(ish) memory complexity
- Produce results incrementally (streaming)
- Send results to client periodically

## Visualize the Data
- D3.js has multiple "pure functions" that work nicely with React Render
- 3 methods do not work well because they interact with the DOM

## Render Target
- SVG
- Cangas
- [React-ART](https://github.com/reactjs/react-art)
- more…

### Considerations
- Number of visual elements
- Animation
- Level of interactivity
- Browser support

### SVG vs Canvas

**SVG**
- CSS Styles
- CSS Animations (+ react transitions)
- DOM Events (+ react events)

**Both**
- 1000 or fewer visual elements

**Canvas**
- More than 1000 visual elements

## Dato Visualization Architecture (GraphLab Canvas)
- 100% React driven
- > 1 TB of data in the browser with little to know

------------------------------------

# React Refracted (a discussion about _Om_)
- David Nolen

> Unfamiliar ≠ Complex

> Big ≠ Complex

_Brunneleschi Dome…bricks herringbone pattern_

## React as a _platform_
- Platform: plan of action, scheme, or design
- A good platform allows you to build something common as well as something amazing…that no one has seen before

> **Mutability** should be an implementation detail

- React works with mutable data AND immutable data

## Om
- Started off as an experiment
- Inspired by paper "Worlds: controlling the scope of side effects" by Alan Kay, and others (Viewpoints Research Institute)

### Concepts / Objectives
- Immutable app state, full stop
- Async rendering via `requestAnimationFrame`
- Jump to any point in time with respect to application state
- Modularity

> This is software…there will probably 4-5 different solutions that address different dimensions of the problem.

## Demo of Global Immutable App State with CircleCI
- http://youtu.be/5yHFTN-_mOo

------------------------------------
