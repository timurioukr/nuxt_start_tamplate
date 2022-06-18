<template>
  <NuxtLink :to="`/products/${ card.id }`" class="card-container">
    <img :src="require(`@/assets/images/${ card.image || 'fe1.jpg' }`)" alt="fe" class="image">
  </NuxtLink>
</template>

<script>
export default {
    props: {
        card: Object
    }
}
</script>

<style scoped>

.card-container {
  width: 24%;
  border-radius: 0.5rem;
  overflow: hidden;
  margin-bottom: 1.5rem;
  cursor: pointer;
}
.image {
  width: 100%;
  height: 100%;
}

</style>
