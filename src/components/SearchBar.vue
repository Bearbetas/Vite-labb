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
      try {
        const response = await fetch(`https://pokeapi.co/api/v2/pokemon/${this.PokemonName.toLowerCase()}`);
        const result = await response.json();
        this.pokemon = result;
        this.image = result.sprites.front_default; // Add this line to set the image URL
      } catch (error) {
        console.error('Error fetching data:', error);
      }
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
          <div id="answer" v-if="pokemon"><h3>It's {{pokemon.name}}!</h3>
            <ul>
            <!-- <li> {{pokemon.type.name}} </li>   funkar ej?? --> 
            <li>Height: {{ pokemon.height }}0 cm </li>
            <li>Weight: {{ pokemon.weight }} Hecto</li>
            <li>Index number: {{ pokemon.id }} </li>
          </ul>
          <img id="Sprite" :src="pokemon.sprites.front_default" alt="Pokemon Image" />
          </div> 
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
  padding: 2vh;
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

#answer {
  margin-top: 3%;
  font-size: 25px;
}

</style>