<template>
    Ini Header

    <pre>{{ counter }}</pre>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";
import { computed } from "vue";

const counterStore = useCounterStore();
const counter = computed(() => counterStore.count)

counterStore.$subscribe((mutation, state) => {
    console.log(mutation, state);
});
</script>