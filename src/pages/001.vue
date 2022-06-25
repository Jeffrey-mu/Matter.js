<script setup lang="ts">
import Matter from 'Matter-js'
function init() {
  // module aliases
  const { Engine, Render, Runner, Bodies, Composite } = Matter

  // create an engine
  const engine = Engine.create()

  // create a renderer
  const render = Render.create({
    element: document.getElementById('box'),
    engine,
  })

  // create two boxes and a ground
  const boxA = Bodies.rectangle(100, 200, 80, 80)
  const boxB = Bodies.rectangle(100, 50, 80, 80)
  const ground = Bodies.rectangle(100, 200, 410, 60, { isStatic: true })

  // add all of the bodies to the world
  Composite.add(engine.world, [boxA, boxB, ground])

  // run the renderer
  Render.run(render)

  // create runner
  const runner = Runner.create()

  // run the engine
  Runner.run(runner, engine)
}
onMounted(init)
</script>

<template>
  <div id="box" h-100 w-100 b-1 overflow-hidden />
</template>
