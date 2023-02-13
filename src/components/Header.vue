<template>
    Ini Header

    <pre>state : {{ counter }}</pre>
    <pre>getter : {{ getCount }}</pre>
    <pre>getters : {{ doubleCount }}</pre>
    <pre>getters :{{ dividedByTwo }}</pre>
    <pre>pokemon : {{ pokemon }}</pre>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";
import { computed } from "vue";
import { usePokemonStore } from "../stores/pokemon"

const counterStore = useCounterStore();
const pokemonStore = usePokemonStore();

const counter = computed(() => counterStore.count);
const getCount = computed(() => counterStore.count);
const doubleCount = computed(() => counterStore.doubleCount);
const dividedByTwo = computed(() => counterStore.dividedBy(2));

const pokemon = computed(() => pokemonStore.pokemonDetails);

counterStore.$subscribe((mutation, state) => {
    console.log(mutation, state);
});
</script>