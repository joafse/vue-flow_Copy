# Vue Flow 🌊

Vue Flow: A highly customizable Vue 3 Flowchart component.

## Table of contents

- [Vue Flow 🌊](#vue-flow-)
  - [Table of contents](#table-of-contents)
  - [⭐️ Features](#️-features)
  - [🎮 Quickstart](#-quickstart)

## ⭐️ Features

- 👶 __Easy setup__: Get started hassle-free - Built-in zoom- & pan features, element dragging, selection and much more

- 🎨 __Customizable__: Use your custom nodes, edges and connection lines and expand on Vue Flows' functionality

- 🚀 __Fast__: Tracks changes reactively and only re-renders the appropriate elements

- 🧲 __Utils & Composition__: Comes with graph helper and state composable functions for advanced uses

- 📦 __Additional Components__:

  - 🖼 Background: With two built-in patterns and some configuration options like height, width or color.

  - 🧭 Minimap: Shows current nodes in a small map shape in the bottom right corner

  - 🕹 Controls: Control zoom behavior from a panel on the bottom left

  - 🤖 And (many) more to come...

- 🦾 __Reliable__: Fully written in TypeScript


## 🎮 Quickstart

In Vue Flow, an application structure consists of __nodes__ and __edges__, all of which are categorised as __elements__.

__Each element requires a unique id.__

Nodes additionally need an __XY-position__, while edges require a __source__ and a __target__, both represented by node ids.

```vue
<!-- Flowchart.vue -->
<script setup>
import { ref } from 'vue'  
import { VueFlow } from '@vue-flow/core'

const nodes = ref([
  { id: '1', type: 'input', label: 'Node 1', position: { x: 250, y: 5 } },
  { id: '2', label: 'Node 2', position: { x: 100, y: 100 } },
  { id: '3', label: 'Node 3', position: { x: 400, y: 100 } },
  { id: '4', label: 'Node 4', position: { x: 400, y: 200 } },
])
  
const edges = ref([
  { id: 'e1-2', source: '1', target: '2', animated: true },
  { id: 'e1-3', source: '1', target: '3' },
])
</script>

<template>
  <VueFlow v-model:nodes="nodes" v-model:edges="edges"></VueFlow>
</template>
```

⚠️ __Make sure to import the necessary styles:__

```css
/* import the required styles */
@import "@vue-flow/core/dist/style.css";

/* import the default theme (optional) */
@import "@vue-flow/core/dist/theme-default.css";
```

Do __not__ scope these styles with `scoped` in your component.


This project is built with

- [D3.js]
  - D3 makes all the zoom and pan actions in Vue Flow possible.

- [VueUse]
  - VueUse is a collection of essential vue composition utilities
