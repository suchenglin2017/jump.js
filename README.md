# Jump.js

A small, modern, dependency-free smooth scrolling library.

## Usage

Jump was developed with a modern JavaScript workflow in mind. To use it, it's recommended you have a build system in place that can transpile ES6, and bundle modules. For a minimal boilerplate that fulfills those requirements, check out [outset](https://github.com/callmecavs/outset).

Follow these steps to get started:

* [Install](#install)
* [Instance](#instance)
* [Jump](#jump)

### Install

Using NPM, install Jump.js, and add it to your package.json dependencies.

```bash
$ npm install jump.js --save
```

### Instance

Simply import Jump, then instantialize it. No options are passed to the constructor:

```es6
// import Jump
import Jump from 'jump.js'

// create an instance
const Jump = new Jump()
```

It's recommended that you assign your Jump instance to a variable. One instance can make infinite jumps.

### Jump

Two parameters are required to make a jump:

* A [target](#target)
* An [options](#options) object

#### Target

To jump to an element, pass a CSS selector as a string.

```es6
Jump.jump('.selector', {
  // ...
})
```

To scroll from the current position, pass a number of pixels, positive or negative.

```es6
// down one viewport height
Jump.jump(window.innerHeight, {
  // ...
})

// up 100px
Jump.jump(-100, {
  // ...
})
```

#### Options

Note that **duration is required** for every `jump()`.

Defaults are shown below:

```es6
Jump.jump('.selector', {
  duration: /* REQUIRED, no default */,
  offset: 0,
  callback: undefined
})
```

Explanation of each option follows:

##### duration

How long the `jump()` takes, in milliseconds.

```es6
Jump.jump('.selector', {
  duration: 1000
})
```

##### offset

Offset a `jump()`, _only if to an element_, in pixels.

Useful for accomodating elements fixed to the top/bottom of the screen.

```es6
Jump.jump('.selector', {
  offset: 100
})
```

##### callback

Fired after the `jump()` has been completed.

```es6
Jump.jump('.selector', {
  callback: () => {
    console.log('Jump completed!')
  }
})
```

## Browser Support

Jump depends on the following browser APIs:

* [requestAnimationFrame](https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame)

Consequently, it supports the following natively:

* Chrome 24+
* Firefox 23+
* Safari 6.1+
* Opera 15+
* IE 10+
* iOS Safari 7.1+
* Android Browser 4.4+

To add support for older browsers, consider including polyfills/shims for the APIs listed above. There are no plans to include any in the library, in the interest of file size.

## License

MIT. © 2015 Michael Cavalea

[![Built With Love](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com)
