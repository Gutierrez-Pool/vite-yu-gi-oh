<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import AppCards from './components/AppCards.vue';
import CardSearch from './components/CardSearch.vue';

export default {

  data() {
    return {
      cards: [],
      store,
    }
  },

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
      console.log(res.data.data)
      this.store.cards = res.data.data
    })
  },

  components: {
    AppNav,
    AppCards,
    CardSearch,
  },

  methods: {

    filterCards() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(res => {

        this.store.filters = res.archetype

      });
    }
  },
}
</script>

<template>

  <AppNav></AppNav>
  <div class="container">
    <CardSearch @filter="filterCards()"></CardSearch>
    <AppCards></AppCards>
  </div>


</template>

<style>



</style>
