<script>

export default {
  data() {
    return {
      PokemonName: '',
      pokemon: null,
    }
    },
  methods: {
    async fetchData() {
  const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${this.PokemonName}`);
  const result = await response.json();
  this.pokemon = result;
  },
  onClick() {
    this.fetchData();
  },
}
}
</script>


<template>
      <div id="SearchBar">
      <div id="searchbox">
        <h2>Who's that Pokémon?</h2>
        <div class="SearchHere">
          <input id="title" v-model= "PokemonName" placeholder="Enter Pokémon" />
          <input id="search" @click="onClick" type="button" value="Search" />
          <div id="answer" v-if="pokemon">It's {{pokemon.name}}! 
            Number Id:{{ pokemon.id }} 
            Height:{{ pokemon.height }}0 cm 
            Weight: {{ pokemon.weight }} hecto

            {{ pokemon.sprites.front_default }}</div>
        </div>
      </div>
    </div>


</template>

<style scoped>

h2 {

  margin-bottom: 2vh;
  font-family: 'Oswald', sans-serif;
  font-size: 5vh;

}
#SearchBar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right:20vh;
  margin-left: 20vh;
  background-color:azure;
  border-radius: 7px;
  border-color: black;
  border-style: double;
  border-width: 1vh;

}
.SearchHere {
  display: flex;
  flex-direction: column;
  max-width: 350px;
margin: auto;
}

#search {
margin: 2vh;
  padding: 10px;
  background-color:black;
  border-radius: 20px;
  color: white;
  font-size: 17px;
  cursor: pointer;
}

#title {
  padding: 10px;
  font-size: 17px;
  border-radius: 20px;
  color: rgb(8, 8, 8);
  border: 1px solid grey;
}

#searchResults {
  margin-top: 3%;
  font-size: 25px;
}

</style>