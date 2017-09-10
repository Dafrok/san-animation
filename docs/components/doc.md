# <img src="https://ecomfe.github.io/san/img/logo-colorful.svg" height="28px"><span>San Transition</span>

High order component factory for generating [san](//github.com/ecomfe/san) components with transition effects.

## Get Start

### Installation

#### NPM

```bash
$ npm install --save san-transition
```

#### CDN

```html
<script src="//unpkg.com/san-transition"></script>
```

### Usage

```html
<template>
  <div>
    <transition-layer>A component with transition effects.</transition-layer>
  <div>
</template>

<script>
import {transition} from 'san-transition'
import {YourComponent} from 'YOUR_SAN_COMPONENT'

export default {
  components: {
    'transition-layer': transition('fade')(YourComponent)
  }
}
</script>

<style>
.fade-live {
  opacity: 1;
  transform: translate(0, 0);
  transition: all .5s;
}
.fade-in, .fade-out {
  opacity: 0;
  transform: translate(100px, 0);
}
</style>

```

## API

### transition

- Arguments
  - **{None, String, Object}** hook id
- Usage
  ```javascript
  // register default hooks
  // the same as `transition('san')(YourComponent)`
  transition()(YourComponent)

  // register named hooks
  transition('foo')(YourComponent)

  // register custom hooks
  transition({
    in: 'custom-transition-in-hook'
    out: 'custom-transition-out-hook',
    live: 'custom-live-hook',
  })(YourComponent)
  ```

### transitionGroup (uncompleted)

Coming soon...

## CSS Hooks

- **in** - Applies when the component attaches DOM tree and removes in the next frame immediately.
- **out** - Applies when the component will dispose.
- **live** - Applies between the next frame of ***in*** hook deactives and ***out*** hook actives.

## Try It Out

### Default Hooks

<try penId="pwravg" title="Default Hooks"></try>

### Named Hooks

<try penId="VWzQWV" title="Named Hooks"></try>

### Custom Hooks

<try penId="xrLYYz" title="Custom Hooks"></try>

### Keyframe Animation Transition

<try penId="rwzJqJ" title="Keyframe Animation Transition"></try>

### Working with s-if & s-else expression

<try penId="dRzmbB" title="Working with s-if & s-else expression"></try>