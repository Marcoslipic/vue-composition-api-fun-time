<template>
<h2>{{ state.count }}, doubled = {{state.double}}</h2>
<button @click="updateCount(true)">increment Value</button>
<button @click="updateCount(false)">Decrease Value</button>
</template>

<script>
import { reactive, computed } from 'vue'

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2)
    });

    function updateCount(increase){
      if (increase){
        state.count++
      } else {
        state.count--;
      }
    }

    return {
      state,
      updateCount
    }
  }
}
</script>

<style>

</style>
