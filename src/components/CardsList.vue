<template>
  <div class="cards-list">
    <CardsLook v-for="card in cards" :key="card.id" :name="card.name" :type="card.type" :desc="card.desc"
      :image="card.card_images[0].image_url" />
  </div>
</template>

<script>
import CardsLook from "./CardsLook.vue";

export default {
  components: {
    CardsLook,
  },
  data() {
    return {
      cards: [],
    };
  },
  async created() {
    await this.fetchCards();
  },
  methods: {
    async fetchCards() {
      try {
        const response = await fetch(
          "https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Red-Eyes"
        );
        const data = await response.json();
        this.cards = data.data;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
<style scoped>
.cards-list {
  display: flex;
  flex-wrap: wrap;
}
</style>
