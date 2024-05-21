<template lang="">
    <div>
        <button @click="increment" id="counter-button">Increment</button>
        <p>Count: {{ count }}</p>
    </div>
</template>
<script>
export default {
    data() {
        return {
            count: 100
        }
    },
    methods: {
        increment() {
            this.count++
        }
    },

}
</script>
<style lang="css">
#counter-button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    border-radius: 20px;
}
</style>
