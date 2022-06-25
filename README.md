# Matter.js
Matter.js is a 2D physics engine for the web

## Getting started
### Install
```shell
pnpm install matter-js
```


### Usage example
The following is a minimal example using the built in renderer and runner to get you started:

```js
// module aliases
const { Engine, Render, Runner, Bodies, Composite } = Matter
// create an engine
const engine = Engine.create()

// create a renderer
const render = Render.create({
  element: document.body,
  engine
})

// create two boxes and a ground
const boxA = Bodies.rectangle(400, 200, 80, 80)
const boxB = Bodies.rectangle(450, 50, 80, 80)
const ground = Bodies.rectangle(400, 610, 810, 60, { isStatic: true })

// add all of the bodies to the world
Composite.add(engine.world, [boxA, boxB, ground])

// run the renderer
Render.run(render)

// create runner
const runner = Runner.create()

// run the engine
Runner.run(runner, engine)
```