<template>
  <div class="container">
    <h4 class="header">All workers</h4>
    <p class="snippet">Change your workers</p>
    <div class="cards-container">
      <LargeCard
        v-for="card in cardsSection"
        :key="card.id"
        :card="card"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cardsSection: Array,
  },
};
</script>

<style scoped>
.container {
  margin-top: 2rem;
}
.header {
  font-weight: 700;
  font-size: 1.5rem;
}
.snippet {
  color: grey;
  margin-bottom: 1.5rem;
}
.cards-container {
  display: flex;
  justify-content: space-between;
}
@media (max-width: 768px) {
  .cards-container {
    flex-direction: row;
    align-items: center;
    justify-content: space-around;
    flex-wrap: wrap;
    align-items: flex-start;
  }
  .container {
    text-align: center;
  }
}
</style>
