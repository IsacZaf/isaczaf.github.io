<script>
import CardsList from './components/CardsList.vue'
import CardsLook from './components/CardsLook.vue'

export default {
  components: {
    CardsList,
    CardsLook
  }
}
</script>

<template>
  <div>
    <CardsLook />
    <CardsList />
  </div>
</template>

