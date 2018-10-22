<template>
    <div>
        <button v-on:click="increment">+</button>
        <span>{{count}}</span>
        <button v-on:click="decrement">-</button>
    </div>
</template>

<script>
import {mapActions} from 'vuex';
export default {
    name: 'count',
    computed: {
        count() {
            return this.$store.state.count;
        }
    },
    methods: {
        increment() {
            this.$store.commit('increment');
        },
        ...mapActions([
            'decrement'
        ])
    }
}
</script>
