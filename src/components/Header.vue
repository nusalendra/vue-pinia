<template>
    Ini Header

    <pre>{{ counter }}</pre>
    <pre>{{ getCount }}</pre>
    <pre>{{ doubleCount }}</pre>
    <pre>{{ dividedByTwo }}</pre>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";
import { computed } from "vue";

const counterStore = useCounterStore();
const counter = computed(() => counterStore.count);
const getCount = computed(() => counterStore.count);
const doubleCount = computed(() => counterStore.doubleCount);
const dividedByTwo = computed(() => counterStore.dividedBy(2));

counterStore.$subscribe((mutation, state) => {
    console.log(mutation, state);
});
</script>