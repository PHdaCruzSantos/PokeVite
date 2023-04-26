<script setup>
  const pokemon = defineProps(['name', 'svg', 'img'])
</script>
<template>
  <div class="card">
    <img 
    :src="img"
    height="250"
    class="card-img-top pt-2" 
    :alt="pokemon.name"
    >
    <div class="card-body">
      <h5 class="card-title text-center">{{ pokemon.name }}</h5>
      <hr>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    </div>
  </div>
</template>


<style scoped>

</style>