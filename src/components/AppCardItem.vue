<script>
export default {
    name: 'AppCardItem',

    props: {
        card: Object,
    },
}
</script>

<template>
    <li class="card">
        <img :src="card.card_images[0].image_url_small" :alt="card.name">
        {{ card.name }}
        {{ card.type }}
    </li>
</template>

<style lang="scss">


</style>