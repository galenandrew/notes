# Introduction to Ember.js
@date 2014-08-18

## Speakers
- **Jeremy Brown**
- Joshua (Josh) Cochran
- Matthew Marcum

## Resources
- [Ember CLI](http://www.ember-cli.com/)
- EZ - Ember Zone
- Ember London (Vimeo)
- Ember Inspector
- Real World Fixtures by Chris Ball (speaker deck) - Using a mock API server during development
- Ember Weekly (newsletter)
- [Architecture Diagram](http://smashingmagazine.com/wp-content/uploads/2013/09/ember-sketch.png)

## What is Ember.js
> A framework for creating ambitious web applications

- The next generation of frameworks (Backbone/Angular/Ember)
- Built for productivity
- Opinionated - "You don't have to drink the coolaid, but the coolaid tastes great!"
- Sometimes perceived as difficult to learn
- Well organized

## Parts of Ember
- Model
- Routes
- Templates
- Views
- Controllers
- Components

## Model
- An **object** that stores persistent state
- Templates are responsible for displaying the model to the user by turning it into HTML
- In many applications, models are loaded via an HTTP JSON API, although Ember is agnostic to the backend that you choose
- _Business Logic typically resides here_

## Routes
- URL representations of your application's objects, telling the template which model it should display (such as a url of `/cars` renders a collection of cars)
- Queries the model and makes it available in the controller and templates
- As the templates or models being shown to the user change, Ember automatically keeps the URL in the browser's address bar up-to-date
- This means that, at any point, users are able to share the URL of your app. When someone clicks the link, they reliably see the same content as the original user
- Can also…
	- …set properties in controllers
	- …execute events and actions
	- …connect a particular template to a particular ???
- _Application Logic typically resides here_

## Templates
- The HTML (user interface) of your application
- Each template is backed by a model, acccessed via the controller, and the template automatically updates itself if the model changes
- Written in the Handlebars templating language

> Handlebars was written by/for Ember!

- So they can include things such as…
	- …other tempaltes
	- …usual logic such as `if` and `else
	- …loops
	- …formatting helpers
	- …expressions
	- …outlets
	- …components

## Views
_YOU DO NOT NEED TO HAVE A VIEW_
- Represent the visual parts of your application that the user can see in the browser
- Associated with a controller, a handlebars template and a route
- Handle events or custom interactions that are impossible to manage from templates
- `didInsertElement` hook where you can interact with jQuery very easily
- Become extremely useful when you need to build reusable views such as modals, popovers, date-pickers and autocomplete fields

## Controllers
- Objects that store application state
- Have a model set on them by a route
- Act as a bridge between the model and the view or template
- A template can retrieve properties from both the model and a controller
- Are auto-generated if not explicitly defined
- Allow you to decorate your models with display logic
- In general, your models will have properties that are saved to the server, while controllers will have properties that your app does not deed to save to the server
- Can override model data (template -> controller -> model)

**Three Different Types of Controllers**
1. Controller
	- Value Store
2. ObjectController
	- Represents a single model
3. ArrayController
	- Represents an array of models


- If you don't specifically define a controller for a route, Ember will automatically make one for you based on the return value of the route's model hook
	- Eg. Model returns an object -> ObjectController is created, Model returns an array -> ArrayObject is created, Model does not return anything, a default controller is returned

## Components
- A completely isolated View that has no acces to the surrounding context
- A great way to build reusable components for your applications
- Like Widgets, but much more restrictive

# Concepts
- **Route** controls your application
- **Controllers** "decorate" your data
- Ultimately **Controllers** are also optional

## Naming Conventions
- When your application boots (URL `/`), Ember will look for these objects:
	- `App.ApplicationRoute`
	- `App.ApplicationController`
	- the application template
- If your user navigates to `/favorites`, Ember will look for these objects:
    - `App.FavoritesRoute`
    - `App.FavoritesController`
    - the favorites template (eg `favorites.hbs`)

## Organizing an Ember Application
- Single File App (gross)
- Multiple Files and Directories
    - Requires it to be compiled/built into a single application file (via Grunt, Brunch, Mimosa, or Broccoli)
    - Strongly recommend Ember CLI

## Gotchya's
- Ember CLI uses ES6 transpiler
