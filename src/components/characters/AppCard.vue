<script>
import { store } from '../../data/store';
export default {
    name: 'AppCard',
    data() {
        return {
            store
        }
    }
}
</script>



<template>
    <div class="col">
        <div class="mycard">
            <img :src="store.pokemonList.imageUrl" :alt="store.pokemonList.name">
            <p> #{{ store.pokemonList.number }}</p>
            <h3>{{ store.pokemonList.name }}</h3>
            <p>{{ store.pokemonList.ability1 }}</p>
        </div>
    </div>
</template>



<style scoped lang="scss">
.mycard {
    padding: 15px;
    background-color: white;
    margin: 15px 0;
    border-radius: 20px;

    img {
        width: 100%;
        height: 200px;
    }
}
</style>