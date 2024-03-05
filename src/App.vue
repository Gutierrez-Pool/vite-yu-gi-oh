<script>
import axios from 'axios';
import {store} from './store.js';

import AppNav from './components/AppNav.vue';
import AppCards from './components/AppCards.vue';

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
  },
}
</script>

<template>

  <AppNav></AppNav>
  <div class="container">
    <AppCards></AppCards>
  </div>


</template>

<style>



</style>
