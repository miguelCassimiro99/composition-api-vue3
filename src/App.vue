<template>
  <div>
    <p>Spaces Left: {{ spacesLeft }} out of {{ capacity }}</p>
    <h2>Attending</h2>
    <ul>
      <li v-for="(name, index) in attending" :key="index">
        {{ name }}
      </li>
    </ul>
    <button @click="increaseCapacity()">Increase Capacity</button>
  </div>
</template>

<script>
import {ref, computed } from 'vue'

export default {
  setup() {

    // using ref we create an reference to a primary
    // To access 'capactiy' value, we need to use
    // capacity.value because capacity it's a object of a reference and it's value its equal to 3
    const capacity = ref(3)
    const attending = ref(['Miguel', 'Vinicius', 'Marcus'])
    
    // function like methods
    function increaseCapacity() {
      capacity.value++;
    }

    // Here's the way we use computed props on Vue 3 with Composition API method
    // We create a function
    const spacesLeft = computed(() => {
      return capacity.value - attending.value.length;
    })

    return {
      capacity, increaseCapacity, spacesLeft, attending
    }
  }
}

/*
We have another option to 'ref'
Its reactive
on this option, it's similar ao to the data() of old version

import {reactive} from 'vue'

setup() {
  const event = reactive({
    capaticy: 4,
    attending: [],
    spacesLeft: computed(() => {})
  })

  return { event }
}

on this way whe don't need to use '.value' of a data because
it's already reads the .value.
Also, on template, we need to use {{ event.capacity }} as Ex.
Because we returning the event object


To use an object destructor we need to use a function toRefs(event)
*/
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
