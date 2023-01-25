<script>
import { store } from '../../data/store';
export default {
    name: 'AppCard',
    props: {
        pokemon: Object
    }
}
</script>



<template>
    <div class="col">
        <div class="mycard">
            <img :src="pokemon.imageUrl" :alt="pokemon.name">
            <p> #{{ pokemon.number }}</p>
            <h3>{{ pokemon.name }}</h3>
            <p>{{ pokemon.ability1 }}</p>
        </div>
    </div>
</template>



<style scoped lang="scss">
.mycard {
    padding: 15px;
    background-color: white;
    margin: 15px 0;
    border-radius: 20px;
    text-align: center;

    img {
        width: 100%;
        height: 150px;
        margin: 20px 0;
    }
}
</style>