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
        <strong>
            {{ card.name }}
        </strong>
        <small>
            {{ card.type }}
        </small>
    </li>
</template>

<style lang="scss">
@use '../styles/variables' as *;

.card {
    display: flex;
    flex-flow: column;

    width: calc(100% / 5 - $cardListGap / 5 * 4);

    gap: 1em;

    text-align: center;

    border-radius: 10px;
    background-color: #d48f38;
}


</style>