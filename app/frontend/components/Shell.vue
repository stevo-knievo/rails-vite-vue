<template>
  <div>
    <p>Shell Vue2 Component 1</p>
    <v-btn block disabled elevation="2" fab large outlined plain raised rounded tile>Hallo </v-btn>
    <v-btn v-on:click="increment" prepend-icon="$vuetify" append-icon="$vuetify">
      Increment
    </v-btn>
    <p>Counter: {{ counter }}</p>
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
