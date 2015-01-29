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

## Demo
_…absolutely amazing!!…_
