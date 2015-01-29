# Day One Sessions

------------------------------------

# Keynote
- Tom Occhino

> Announced React Native

------------------------------------

# Tweak your page in real time, without leaving the comfort of your editor
- Speaker: Brenton Simpson @appsforartists

## Links
- http://webpack.github.io
- http://gaearon.github.io/react-hot-loader/
- https://github.com/appsforartists/ambidex

------------------------------------

# Unlocking the structure of your React applications with the AST
- Gurdas Nijor @gnijor

## Webpack
- Module Bundler
- Loaders

------------------------------------

# Data fetching for React applications at Facebook
- Daniel Schafer @dlschafer and Jing Chen @jingc

## Flux
> One way flow of data to minimize interactions with it.

## GraphQL
- Query language that Facebook uses to define data requirements and define the response schema

## Relay
- Next evolution of Flux architecture

------------------------------------

# Channels and Communicating Sequential Processes
- James Long

## Misc / Research
- **js-csp**
- Concepts of channels/streams vs promises (in order to use promises you have to continually wrap them in promises)
- Generators

------------------------------------

# react-router increases your productivity
- Michael Jackson @mjackson
- Ryan Florence @rpflorence

**It all started here…**
https://twitter.com/mjackson/status/466286956989542400

[Removing User Interface Complexity, or Why React is Awesome](http://jlongster.com/Removing-User-Interface-Complexity,-or-Why-React-is-Awesome)

> "If your user interface is nested, your routes should also be nested." - Yehuda Katz

> "Cool URIs don't change" - Tim Berners-Lee

- URLs should be part of your design process

## Transitions
- When the URL does change…what happens
- Example: https://github.com/rackt/react-router/blob/master/examples/auth-flow/app.js

------------------------------------

# The future of JavaScript layout systems
- Pete Hunt @petehunt @floydophone

**Full Stack Flux**

- What is a flux store?
> reduce() + "change event"

> "You jump off a cliff and assemble an airplane on the way down" - Reid Hoffman

- Re

_Turning the Database Inside Out_ - A talk by Martin…?

------------------------------------

# Making your app fast with high-performance components
- Jason Bonta @jbonta

_React is made up of **props** and **states**_

## Pure Components
- Render only depends on props and state

## Re-renders
- `shouldComponentUpdate`
- **PureRender** mixin (prevents component from re-rendering as a result of it's parent…insulates the component)

## Data Comparability
- Easy to compare simple data types
- Retail Store Model (Returning a product…not opened)
- Immutable data makes comparing complex data types easy `ref1 === ref2`

## Loosely coupled component hierarchy


## Containers vs Components
- Containers talk to store
- Components render markup

## Basic concepts for optimization
1. Purity
    - Use `shouldcomponentupdate`
2. Data Comparability
    - use immutable
3. Loose Coupling
    - use for both maintainability
    -
4. Children
    - are expensive
    - should exercise independence


## FixedDataTable
facebook.github.io/fixed-data-table

------------------------------------

# React.js & i18n
- Eric Ferraiuolo @ericf

- `Intl.NumberFormat`
- `Intl.DateTimeFormat`
- `Intl.Collator`

https://github.com/andyearnshaw/Intl.js/

------------------------------------

# Hype!
- Ryan Florence @rpflorence

## Demos
- https://github.com/rpflorence/react-magic-move
- https://github.com/rackt/react-modal
- http://react.rocks/example/react-router-mega-demo
