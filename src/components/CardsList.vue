<template>
  <div>
    <h1>Yugioh Cards</h1>
    <ul v-if="cards.length">
      <li v-for="card in cards" :key="card.id">
        <Card :card="card" />
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
import Card from './Card.vue'

export default {
  components: {
    Card
  },
  data() {
    return {
      cards: []
    }
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then(response => {
        this.cards = response.data.data
      })
      .catch(error => {
        console.log(error)
      })
  }
}
</script>
