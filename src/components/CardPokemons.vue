<script setup>
  // const pokemon = defineProps(['name', 'svg', 'img', 'types'])
  const pokemon = defineProps({
    name: String,
    img: String,
    types: Array
  })
</script>
<template>
  <div class="card">
    <img
      v-if="pokemon.name" 
      :src="img"
      height="250"
      class="card-img-top pt-2" 
      :alt="pokemon.name"
    >
    <img
      v-else
      src="../assets/egg_pokemon.svg"
      height="250"
      class="card-img-top pt-2" 
    >
    <div class="card-body">
      <h5 class="card-title text-center">{{ pokemon.name }}</h5>
      <hr>
      <div 
        v-if="pokemon.types"
        class="d-flex justify-content-center"
      >
      
      <h1>Types:
        <span
          v-for="type in pokemon.types"
          :key="type.type.name"
          class="badge bg-secondary ms-2"
        >
          {{ type.type.name }}
        </span>
      </h1>


      </div>
    </div>
  </div>
</template>


<style scoped>

</style>