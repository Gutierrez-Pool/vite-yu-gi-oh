<script>
import AppCardItem from './AppCardItem.vue';
import { store } from '../store.js';

export default {
    name: 'AppCards',

    components: {
        AppCardItem,
    },

    data() {
        return {
            store,
        }
    },
}
</script>

<template>

    <main>
        <ul>
            <AppCardItem
                v-for="currentCard in store.cards"
                :card="currentCard"
            ></AppCardItem>
        </ul>

    </main>

</template>

<style lang="scss">
main {
    background-color: #d48f38;
    height: 100vh;
}
</style>