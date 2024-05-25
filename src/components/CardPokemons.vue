<script setup>
// const pokemon = defineProps(['name', 'svg', 'img', 'types'])
const pokemon = defineProps({
  name: String,
  img: String,
  types: Array,
  clear: Function,
});
</script>
<template>
  <div class="card">
    <div class="card-header">
      <button
        v-show="pokemon.name"
        type="button"
        class="btn-close float-end"
        @click="pokemon.clear"
      >
        <span aria-hidden="true"></span>
      </button>
    </div>
    <img
      v-if="pokemon.name"
      :src="img"
      height="250"
      class="card-img-top pt-2"
      :alt="pokemon.name"
    />
    <img
      v-else
      src="../assets/egg_pokemon.svg"
      height="250"
      class="card-img-top pt-2"
      alt="egg_pokemon"
    />
    <div class="card-body">
      <h5 class="card-title text-center">{{ pokemon.name }}</h5>
      <hr />
      <div v-if="pokemon.types" class="d-flex justify-content-center">
        <h1>
          <span
            v-for="type in pokemon.types"
            :key="type.type.name"
            class="badge ms-2"
            :class="type.type.name"
          >
            {{ type.type.name }}
          </span>
        </h1>
      </div>
    </div>
  </div>
</template>


<style scoped>
.normal {
  background-color: #a8a77a;
}
.fire {
  background-color: #ee8130;
}
.water {
  background-color: #6390f0;
}
.electric {
  background-color: #f7d02c;
}
.grass {
  background-color: #7ac74c;
}
.ice {
  background-color: #96d9d6;
}
.fighting {
  background-color: #c22e28;
}
.poison {
  background-color: #a33ea1;
}
.ground {
  background-color: #e2bf65;
}
.flying {
  background-color: #a98ff3;
}
.psychic {
  background-color: #f95587;
}
.bug {
  background-color: #a6b91a;
}
.rock {
  background-color: #b6a136;
}
.ghost {
  background-color: #735797;
}
.dragon {
  background-color: #6f35fc;
}
.dark {
  background-color: #705746;
}
.steel {
  background-color: #b7b7ce;
}
.fairy {
  background-color: #d685ad;
}
</style>
