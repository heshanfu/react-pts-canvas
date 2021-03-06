# react-pts-canvas

[![NPM](https://img.shields.io/npm/v/react-pts-canvas.svg)](https://www.npmjs.com/package/react-pts-canvas)

![cover](./example/cover.png)

This is a React Component for canvas drawing using [Pts](https://ptsjs.org). Pts is a javascript library for visualization and creative-coding. 


## Install

```bash
npm install --save react-pts-canvas
```

## Examples
- The [example](./example) folder provides a quick example of using PtsCanvas in a React app
- Take a look at more examples in [pts-react-example](https://github.com/williamngan/pts-react-example) repo.

## Quick Start

```jsx
import React, { Component } from 'react'
import PtsCanvas from 'react-pts-canvas'

// Add your own Pts drawing functions
class MyCanvas extends PtsCanvas {
  animate( time, ftime ) {
    // ...
  }
}

// Use the component
class Example extends React.Component {
  render () {
    return (
      <MyCanvas background="#abc" play={true} />
    )
  }
}
```


## Usage

If you are getting started with **Pts**, take a look at the [cool demos](https://ptsjs.org/demo) and read the [guides](https://ptsjs.org/guide).

`PtsCanvas` is a component that you may extend to implement your own drawings and animations on canvas using Pts. Like this:

```jsx
class MyCanvas extends PtsCanvas {
  
  animate (time, ftime, space) { 
    // your code for drawing and animation 
  }

  start (bound, space) { 
    // Optional code for canvas init 
  }

  action: (type, x, y, event) { 
    // Optional code for interaction 
  }

  resize (size, event) { 
    // Optional code for resize 
  }
}
```

There are 4 functions in Pts that you can (optionally) overrides: `animate`, `start`, `resize`, and `action`. [See this guide](https://ptsjs.org/guide/space-0500) to learn more about how these functions work.

Once you have implemented your own canvas, you can use it as a component like this:

```jsx
class Example extends React.Component {
  render () {
    return (
      <MyCanvas background="#abc" play={true} />
    )
  }
}
```

`PtsCanvas` component provides the following props:

- `background`
  - background fill color of the canvas. Default value is "#9ab".
- `resize`
  - A boolean value to indicate whether the canvas should auto resize. Default is `true`.
- `retina`
  - A boolean value to indicate whether the canvas should support retina resolution. Default is `true`.
- `play`
  - A boolean value to set whether the canvas should animate. Default is `true`.
- `touch`
  - A boolean value to set whether the canvas should track mouse and touch events. Default is `true`.
- `name`
  - The css class name of the container `<div>`. Default value is "pts-react". Use this class name to set custom styles in your .css file. 
- `style`
  - Optionally override css styles of the container `<div>`.
- `canvasStyle`
  - Optionally override css styles of the `<canvas>` itself. Avoid using this except for special use cases.


## License

Apache License 2.0. See LICENSE file for details.
Copyright © 2017-2018 by [William Ngan](https://williamngan.com) and contributors.
