<template>
  <div class="hello">
    <input type="text" v-model="search" placeholder="Enter search text" />
    <div v-if="filteredCards.length > 0">
      <ul>
        <li v-for="(card, index) in filteredCards" :key="index">
          {{ card.name }}
        </li>
      </ul>
    </div>
    <div v-else>
      No matching cards found.
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "HelloWorld",
  setup() {
    const cards = ref([
      { name: "Card A", type: "Type 1" },
      { name: "Card B", type: "Type 2" },
      { name: "Card C", type: "Type 1" },
      { name: "Card D", type: "Type 3" },
    ]);
    const search = ref("");

    function filteredCards() {
      if (!search.value) return cards.value;
      return cards.value.filter((card) =>
        card.name.toLowerCase().includes(search.value.toLowerCase())
      );
    }

    return {
      search,
      filteredCards,
    };
  },
};
</script>
