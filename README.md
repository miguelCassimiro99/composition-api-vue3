# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)


### Default Composition API
The default organization and explan each option inside the setup()


### Modularizing
Code refactored keeping able to reuse a function inside other components
Use of Composition Function
1 - Remove the content of setup()
2 - Clipped into a function called useEventSpace()
3 - call useEventSpace inside the setup()
Now the component is organized by feature

- Code reusable across other components
1 - Move the function useEventSpace to another file
/use/event-space.js

2 - Import into our App.vue

3 - return the function on the setup()

4 - create local objets for the data of the Composition Function are sending in.
This solves a problem that mixins charges. Without the local objets, we can't know
which object are been inject by which composition function.