<script setup>
import { onMounted, reactive, ref, computed } from 'vue'
import ListPokemons from '../components/ListPokemons.vue'
import CardPokemons from '../components/CardPokemons.vue'

let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")
let pomkemons = reactive(ref())
let searchPokemonField = ref("")
let pokemonSelected = reactive(ref())

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=151&offset=0")
    .then(res => res.json())
    .then(data => pomkemons.value = data.results)//data equals to the json object
})

const pokemonsFilter = computed(() => {
  if(pomkemons.value && searchPokemonField.value){
    return pomkemons.value.filter(pokemon => pokemon.name.toLowerCase().includes(searchPokemonField.value.toLocaleLowerCase()))
  }
  return pomkemons.value
})

const selectPokemon = async (pokemon) => {
   await fetch(pokemon.url)
    .then(res => res.json())
    .then(data => pokemonSelected.value = data)

  console.log(pokemonSelected.value)
}

</script>

<template>
  <main>
    <div class="container">

      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
          <CardPokemons
            :name="pokemonSelected?.name"
            :img="pokemonSelected?.sprites.other.dream_world.front_default"
          />
        </div>


        
        <div class="col-sm-12 col-md-6">
          <div class="card --cardList">
            <div class="card-body row ">

              <div class="input-group mb-3">
                <span class="input-group-text" id="inputGroup-sizing-default">Search</span>
                <input
                v-model="searchPokemonField"
                type="text"
                class="form-control"
                aria-label="Sizing example input"
                aria-describedby="inputGroup-sizing-default" 
                placeholder="Search Pokemon"
                id="searchPokemonField"
                >
              </div>
              

              <ListPokemons
                v-for="pomkemon in pokemonsFilter"
                :key="pomkemon.name"
                :P_name="pomkemon.name"
                :P_svg="urlBaseSvg + pomkemon.url.split('/')[6] + '.svg'"
                @click="selectPokemon(pomkemon)"
              />
            </div>  
          </div>
        </div>
      </div>


    </div>
  </main>
</template>

<style scoped>
.--cardList {
  max-height: 700px;
  overflow-y: scroll;
  overflow-x: hidden;
  background-color: #eee;
}
</style>