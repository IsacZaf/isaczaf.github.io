<template>
  <div>
    <h1>Yu-Gi-Oh! Cards List</h1>
    <div v-if="loading">Loading...</div>
    <div v-else-if="error">Error: {{ error }}</div>
    <div v-else>
      <ul>
        <li v-for="card in cards" :key="card.id">
          <strong>{{ card.name }}</strong>
          <p>{{ card.type }}</p>
          <p>{{ card.desc }}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardsList",
  data() {
    return {
      cards: [],
      loading: true,
      error: null,
    };
  },
  created() {
    this.fetchCards();
  },
  methods: {
    async fetchCards() {
      try {
        const response = await fetch(
          "https://db.ygoprodeck.com/api/v7/cardinfo.php"
        );
        if (!response.ok) {
          throw new Error(`${response.status} ${response.statusText}`);
        }
        const data = await response.json();
        this.cards = data.data;
        this.loading = false;
      } catch (error) {
        console.error(error);
        this.error = error.message;
        this.loading = false;
      }
    },
  },
};
</script>
