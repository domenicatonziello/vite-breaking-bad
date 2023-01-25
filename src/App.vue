<script>
import axios from 'axios';
import SelectBar from './components/SelectBar.vue';
import { store } from './data/store';
import AppHeader from './components/AppHeader.vue';
import AppCard from './components/characters/AppCard.vue';
export default {
  components: { AppCard, AppHeader, SelectBar },
  data() {
    return {
      store,
      pokemonListUrl: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?',
    }
  },
  methods: {
    fetchPokemonList() {
      this.pokemonListUrl += 'per=10&page=5'
      axios.get(this.pokemonListUrl)
        .then(result => {
          store.pokemonList = result.data.docs;
        })
    },
    filterPokemonTypes(type) {
      this.pokemonListUrl += `eq[${type}]`;
      axios.get(this.pokemonListUrl)
        .then(result => {
          store.pokemonList = result.data.docs;
        })
    }
  },
  mounted() {
    this.fetchPokemonList();
  }
}
</script>

<template>
  <app-header></app-header>
  <select-bar @change-option="filterPokemonTypes"></select-bar>
  <main>
    <div class="container">
      <div class="row row-cols-md-3 row-cols-lg-4 row-cols-xl-5">
        <app-card v-for="pokemon in store.pokemonList" :key="pokemon['_id']"> </app-card>
      </div>
    </div>
  </main>
</template>

<style lang="scss">
@use './assets/scss/style.scss';
</style>