# Canvas requestAnimationFrame
`window.requestAnimationFrame` provides a way to schedule animation updates in between browser repaints. The method takes a callback that will be invoked prior to the next repaint. The function returns a long integer value identifying the scheduled callback, passing this value to `cancelAnimationFrame` will cancel the request. 

The callback is generally called at a rate that matches the display refresh rate and will receive a `DOMHighResTimeStamp` value which indicates the current time. If there are multiple callbacks queued, they will all receive the same timestamp in each cycle of repainting.

```js
...
const updateFrames = (time) => {
 // perform animation updates here
 ...
 // call requestAnimationFrame again, to ensure we update on the next repaint
 requestAnimationFrame(updateFrames)
}

const start = () => requestAnimationFrame(updateFrames);
start();
...
```

## Links
* [MDN - window.requestAnimationFrame](https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame)
* [Gain motion superpowers with requestAnimationFrame](https://medium.com/@bdc/gain-motion-superpowers-with-requestanimationframe-ecc6d5b0d9a4)
