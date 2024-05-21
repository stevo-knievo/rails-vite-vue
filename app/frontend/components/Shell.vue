<template>
  <div>
    <p>Shell Vue2 Component 1</p>
    <p>Counter: {{ counter }}</p>
    <button v-on:click="increment">Increment</button>
  </div>
</template>

<script>
export default {
  data: () => ({
    counter: 0,
  }),
  methods: {
    increment() {
      this.counter++;
    }
  },
}
</script>
