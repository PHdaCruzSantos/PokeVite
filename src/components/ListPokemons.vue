<script setup>
const pokemon = defineProps(['P_name', 'P_svg', 'P_url']) // props: ({ pokemonName: String })


</script>


<template>
  <div class="col-4">
    <div class="card mb-3 p-2 --card"
    >
      
      <p class="text-center">
        {{ pokemon.P_name }}
      </p>
      <img
        :src="P_svg"
        class="card-img-top"
        :alt="pokemon.P_name"
      >

    </div>
  </div>
</template>

<style scoped>
.--card {
  cursor: pointer;
  min-height: 225px;
}

.--card:hover {
 text-transform: uppercase;
}
</style>