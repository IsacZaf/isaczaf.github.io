<template>
  <div id="app">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-view></router-view>
  </div>
</template>

<script>
import CardsList from './components/CardsList.vue'
import About from './components/About.vue'
import { createRouter, createWebHashHistory } from 'vue-router'

const routes = [
  {
    path: '/',
    component: CardsList
  },
  {
    path: '/about',
    component: About
  }
]

const router = createRouter({
  history: createWebHashHistory(),
  routes
})

export default {
  name: 'App',
  router
}
</script>
