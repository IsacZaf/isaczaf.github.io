<template>
  <div id="app">
    <CardsList />
  </div>
</template>

<script>
import CardsList from './components/CardsList.vue'

export default {
  name: 'App',
  components: {
    CardsList
  }
}
</script>

<style lang="scss">
@import '../assets/scss/main.scss'
</style>
