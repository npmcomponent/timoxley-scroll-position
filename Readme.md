*This repository is a mirror of the [component](http://component.io) module [timoxley/scroll-position](http://github.com/timoxley/scroll-position). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/timoxley-scroll-position`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# scroll-position

  Fire events when scrolling over dom elements.

## Installation

    $ component install timoxley/scroll-position

## Example

```js
// Elements we want to track
var items = document.querySelectorAll('div')

var ScrollPosition = require('scroll-position')
var itemPosition = ScrollPosition(items, {
  // Default settings
  offsetOut: 100, // y position in px where items leave the viewport
  offsetIn: 0 // y position where items enter the viewport
})

itemPosition.on('out', function(el) {
  // el was scrolled out of the top of the viewport
  console.log(el)
})
itemPosition.on('in', function(el) {
  // el was scrolled in from the top of the viewport
  console.log(el)
})
itemPosition.on('inOut', function(el) {
  // el was scrolled in or out of the top of the viewport
  console.log(el)
})
```

[Demo](http://timoxley.github.com/scroll-position/examples/menu)

## Events

### out
Fired whenever one of the supplied items is scrolled out the top of the viewport
e.g scrolling down, and the item goes out the top of the viewport.

The first argument to the callback is the element which scrolled out.

### in
Fired whenever one of the supplied items is scrolled into the top of the viewport
e.g scrolling up, and the item enters the top of the viewport.

The first argument to the callback is the element whom scrolled in.

### inOut

Fired whenever one of the target items scrolls in OR out of the top of the viewport.
e.g scrolling up or down, and the item enters or leaves the top of the window.

The first argument to the callback is the element which scrolled in or out.

## License

MIT
