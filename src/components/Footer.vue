<template>
    <button @click="increment">Increment +</button>
    <br>
    <button @click="decrement">Decrement -</button>
    <br>
    <button @click="reset">Reset</button>
    <br><hr>
    <button @click="incrementWithAction">increment with action</button>
    <br>
    <button @click="decrementWithAction">decrement with action</button>
    <br>
    <button @click="incrementByWithAction(5)">increment by with action by 5</button>
    <br>
    <button @click="decrementByWithAction(5)">decrement by with action by 5</button>
    <hr>
    <button @click="fetchPokemon('ditto')">Fetch ditto</button>
    <br>
    <button @click="resetPokemon">reset pokemon</button>
</template>

<script setup>
import { useCounterStore } from "../stores/counter";
import { usePokemonStore } from "../stores/pokemon";

const counter = useCounterStore();
const pokemon = usePokemonStore();

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
};

const incrementWithAction = () => {
    counter.increment()
};

const decrementWithAction = () => {
    counter.decrement()
};

const incrementByWithAction = (amount) => {
    counter.incrementBy(amount)
};

const decrementByWithAction = (amount) => {
    counter.decrementBy(amount)
};

const fetchPokemon = (name) => {
    pokemon.getPokemonDetails(name)
};

const resetPokemon = () => {
    pokemon.$reset()
}

</script>