<template>
  <NuxtLink :to="`/users/${ card.id }`" class="card">
    <img :src="card.avatar" class="image">
    <h3 class="header">{{ card.first_name }}</h3>
    <p class="snippet">{{ card.email }}</p>
  </NuxtLink>
</template>

<script>
export default {
  props: {
    card: Object
  }
};
</script>

<style scoped>
.card {
  padding: 20px;
  width: 100%;
  border: none;
  overflow: hidden;
  cursor: pointer;
}
.image {
  border-radius: 0.5rem;
}
.header {
  font-size: 1.15rem;
  margin-top: 0.4rem;
  color: black;
}
.snippet {
  color: grey;
  font-size: 10px;
}
@media (max-width: 768px) {
  .card {
    padding: 0px;
    width: 30%;
  }
}

</style>