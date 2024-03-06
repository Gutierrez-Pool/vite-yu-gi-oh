<script>
import { store } from '../store.js';

export default {

    name:'CardSearch',

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
            <select name="archetype-filter" id="archetype-filter" @change="$emit('filter')" v-model="store.filtervalue">
                <option 
                    v-for="currentArchetype in store.archetypes"
                    :value="currentArchetype.archetype_name"
                >
                    {{ currentArchetype.archetype_name }}
                </option>
                
            </select>
        </div>

    </div>
</template>