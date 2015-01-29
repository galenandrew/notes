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
