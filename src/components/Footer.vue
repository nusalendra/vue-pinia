<template>
    Ini Footer
    <br>
    <button @click="increment">Increment +</button>
    <br>
    <button @click="decrement">Decrement -</button>
    <br>
    <button @click="reset">Reset</button>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";

const counter = useCounterStore();
const increment = () => {
    counter.$patch((state) => {
        state.count++
    })
};
const decrement = () => {
    counter.$patch((state) => {
        state.count--
    })
};
const reset = () => {
    counter.$reset()
}

</script>