---
title: React
type: usage
order: 103
published: true
---

## Setup

To use modules with [React](https://facebook.github.io/react/), add the mod tag via React's `render` and call `Anymod.render()` when the React component has mounted:

```js
componentDidMount () {
  Anymod.render()
},
render () {
  return <div id="anymod-mldrn"></div>
}
```
<p class="tip">React requires you to use quotation marks (`"`) for attributes.</p>

You can use `Anymod.render()` by itself or with a callback or promise. See the section on [Anymod.render](/v1/api/index.html#Anymod-render-function-options) for more.

## Example

<iframe width="100%" height="700" src="https://jsfiddle.net/component/1vpf4coh/embedded/js,html,result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

## Rendering multiple mods

You can render multiple mods the same way as a single mod. However, React does require that its internal `render` function returns a single element. So to render multiple mods in a single React component, you can wrap them in a common element such as a `<div>`, like so:

```js
render () {
  return (
    <div>
      <div id="anymod-mldrn"></div>
      <div id="anymod-eoako"></div>
      <div id="anymod-amkmr"></div>
    </div>
  )
}
```

## Create React App

If you are using [Create React App](https://github.com/facebook/create-react-app) or another ESLint tool, you may encounter an error along the lines of `'Anymod' is not defined  no-undef`.  In this case, you should add the following to the top of any files using `Anymod.render()`:

`/* global Anymod */`

You can learn more about this solution [here](https://eslint.org/docs/rules/no-undef#rule-details).

## Re-rendering

You can call `Anymod.render()` as often as you'd like in your React component (or elsewhere). This method will not lead to an API call every time; if a mod has already been fetched once, `Anymod.render()` will use that data instead of making another API call.

See the section on [Anymod.render](/v1/api/index.html#Anymod-render-function-options) for more.
