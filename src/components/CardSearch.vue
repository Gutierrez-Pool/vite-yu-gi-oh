<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="container">

        <div id="dropdown">
            <select name="cards" id="cards">
                <option 
                    v-for="currentFilter in store.cards"
                    @click="$emit('filter')"
                    value="archetype"
                >
                    {{ currentFilter.archetype }}
                </option>
                
            </select>
        </div>

    </div>
</template>