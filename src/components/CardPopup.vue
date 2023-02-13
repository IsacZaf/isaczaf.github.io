<template>
    <div class="card-popup" v-if="isOpen">
        <div class="card-popup-overlay" v-on:click="close"></div>
        <div class="card-popup-content">
            <div class="card-popup-image">
                <img :src="card.card_images[0].image_url" :alt="`Image of ${card.name}`" />
            </div>
            <div class="card-popup-description">
                <h2>{{ card.name }}</h2>
                <p>{{ card.desc }}</p>
                <p v-if="card.level">Level/Rank: {{ card.level }}</p>
                <p>Attribute: {{ card.attribute }}</p>
                <p>Type: {{ card.type }}</p>
            </div>
            <button v-on:click="close">Close</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        card: {
            type: Object,
            required: true
        },
        isOpen: {
            type: Boolean,
            required: true
        },
        close: {
            type: Function,
            required: true
        }
    }
}
</script>

<style scoped>
.card-popup {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.card-popup-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
}

.card-popup-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    background-color: #fff;
    border: 1px solid #ccc;
    box-shadow: 2px 2px #ccc;
}

.card-popup-image img {
    max-width: 100%;
    max-height: 100%;
}

.card-popup-description {
    margin-top: 10px;
}

.card-popup-description h2 {
    margin-top: 0;
}

.card-popup-description p {
    margin-bottom: 10px;
}

.card-popup-content button {
    margin-top: 10px;
}
</style>
