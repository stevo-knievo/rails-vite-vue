<template lang="">
    <div>
        <v-btn prepend-icon="$vuetify" append-icon="$vuetify" @click="increment">
        Increment
        </v-btn>
        <p>&nbsp;</p>
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
