# Let's build an isomorphic app with Node, React, and the Flux architecture!
- @event HTML5 Meetup
- @date 2014-01-21
- @speaker Neil Duffy @conceptualitis
- @code https://github.com/conceptualitis/weather-example

_No slides…live coding demo_



## Demo
> _A weather app that lets a user change days and select an hour of the day to view temperature_

### Misc
- Using **Dark Sky API** (weather data)
- Using **Gulp** with **Browserfy** and **reactify** (JHX compiler)
- React can be written in plain _javascript_ or _JHX_ with a compiler
- [**React Devtools**](https://github.com/facebook/react-devtools)

### Application
Using a router (similar to Ember's router) – React Router

### Lifecycle Events
- Deals with application/component _state_

#### `getInitialState`
- Runs at …

#### `componentDidMount`
- Runs when component is

### Flux
Using _Fluxable_ (a flux-like architecture from Yahoo)

#### Architecture (fluxable)
- **Views**: React stuff
- **Action**: View calls
- **Event Pipeline**: Action triggers event, event pipeline listens and respond
- **Store**: Where all the data lives

> No concept of data binding in Flux/React. When any data in the store changes, React calculates diffs in the virtual DOM, then re-renders the elements from the diff
