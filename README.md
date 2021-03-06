# Lit Redux Router

[![npm version][img-npm]][url-npm]
[![Build Status][img-circleci]][url-circleci]
[![Coverage Status][img-codecov]][url-codecov]

[img-npm]: https://img.shields.io/npm/v/lit-redux-router.svg
[img-circleci]: https://circleci.com/gh/fernandopasik/lit-redux-router.svg?style=svg
[img-codecov]: https://codecov.io/gh/fernandopasik/lit-redux-router/branch/master/graph/badge.svg


[url-npm]: https://www.npmjs.com/package/lit-redux-router "npm version"
[url-circleci]: https://circleci.com/gh/fernandopasik/lit-redux-router "Build Status"
[url-codecov]: https://codecov.io/gh/fernandopasik/lit-redux-router "Coverage Status"

Declarative way of routing for [lit-html](https://github.com/Polymer/lit-html) powered by [pwa-helpers](https://github.com/Polymer/pwa-helpers), [redux](https://redux.js.org/) and [lit-element](https://github.com/Polymer/lit-element).

A minimal router solution (~1.25 kb) based on the routing approach taken by [PWA Starter Kit](https://github.com/polymer/pwa-starter-kit).
More info here: https://polymer.github.io/pwa-starter-kit/configuring-and-personalizing/#routing

## Install

```
yarn add lit-redux-router lit-html @polymer/lit-element pwa-helpers redux
```

## Basic Example

```js
// app.js
import { LitElement, html } from '@polymer/lit-element';
import { connectRouter } from 'lit-redux-router';
import store from './store.js';

connectRouter(store);

export default class MyApp extends LitElement {
  render() {
    return html`
      <div class="app-bar">Example App</div>

      <div class="app-content">
        <lit-route path="/"><h1>Home</h1></lit-route>
        <lit-route path="/products/:id?/:name?" component="my-product"></lit-route>
      </div>
    `;
  }
}
```

Check a more complete example in https://github.com/fernandopasik/lit-redux-router/blob/master/example/app.js

## Development

```
yarn watch
yarn test
yarn lint
yarn build
```

## Built with

* [regexparam](https://github.com/lukeed/regexparam) - A tiny (299B) utility that converts route patterns into RegExp
* [lit-html](https://github.com/Polymer/lit-html) - HTML template literals in JavaScript
* [lit-element](https://github.com/Polymer/lit-element) - An ultra-light custom element base class with a simple but expressive API
* [pwa-helpers](https://github.com/Polymer/pwa-helpers) - Small helper methods or mixins to help you build web apps
* [Redux](https://redux.js.org/) - Predictable state container for JavaScript apps

## License

MIT (c) 2018 [Fernando Pasik](https://fernandopasik.com)
