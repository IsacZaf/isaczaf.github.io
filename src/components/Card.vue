<template>
    <div class="card" v-on:click="showDetails(card)">

        <img :src="card.card_images[0].image_url" :alt="`Image of ${card.name}`" />

        <h2>{{ card.name }}</h2>
        <p>{{ card.desc }}</p>
        <p v-if="card.level">Level/Rank: {{ card.level }}</p>

        <p>Attribute: {{ card.attribute }}</p>
        <p>Type: {{ card.type }}</p>
    </div>
</template>

<script>
export default {
    props: {
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
.card {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px;
    max-width: 200px;
    text-align: center;
}

.card img {
    max-width: 100%;
}
</style>
