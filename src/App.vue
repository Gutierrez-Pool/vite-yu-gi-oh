<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import AppCards from './components/AppCards.vue';
import CardSearch from './components/CardSearch.vue';

export default {

  data() {
    return {
      store,

    }
  },

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
      console.log('cards', res.data.data)
      this.store.cards = res.data.data
    });

    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(res => {
        console.log('archetipi', res.data)
        this.store.archetypes = res.data;
    });

  },

  components: {
    AppNav,
    AppCards,
    CardSearch,
  },

  methods: {

    filterCards() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=' + this.store.filtervalue).then(res => {
        console.log('carte', res.data.data)
        this.store.cards = res.data.data;
      });
    },
  },
}
</script>

<template>

  <AppNav></AppNav>
  <div class="container">
    <CardSearch @filter="filterCards"></CardSearch>
    <AppCards></AppCards>
  </div>


</template>

<style>



</style>
