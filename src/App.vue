<script>
import axios from 'axios';
import { store } from './data/store';
import AppHeader from './components/AppHeader.vue';
import AppCard from './components/characters/AppCard.vue';
export default {
  components: { AppCard, AppHeader },
  data() {
    return {
      store
    }
  },
  mounted() {
    axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=5')
      .then(result => {
        store.pokemonList = result.data.docs;
      })
  }
}
</script>

<template>
  <app-header></app-header>
  <main>
    <div class="container">
      <div class="row row-cols-md-3 row-cols-lg-4 row-cols-xl-5">
        <app-card></app-card>
      </div>
    </div>
  </main>
</template>

<style lang="scss">
@use './assets/scss/style.scss';
</style>