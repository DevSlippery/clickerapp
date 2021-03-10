<template>
  <div class="">
    <h2>{{ state.count }}</h2>
    <p>{{ state.double }}</p>
    <button @click="UpdateCount(true)">Increment</button>
    <button @click="UpdateCount(false)">Decrease</button>
  </div>
</template>

<script>
import { reactive, computed } from "vue";
export default {
  name: "App",
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2),
    });
    function UpdateCount(increase) {
      increase ? state.count++ : state.count--;
    }
    return {
      state,
      UpdateCount,
    };
  },
};
</script>

<style>
</style>
