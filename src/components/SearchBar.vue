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
      <div id="textbar">
        <h1>Who's that Pokémon?</h1>
        <div class="SearchHere">
          <p>Please enter a name or a number:</p>
          <input id="title" v-model= "PokemonName" placeholder="Enter Pokémon" />
          <input id="search" @click="onClick" type="button" value="Search" /> 
          <div id= "answerbox" v-if="pokemon"><h2>It's {{pokemon.name}}!</h2>
            <img id="Sprite" :src="pokemon.sprites.front_default" alt="Pokemon Image" />
            <p class="info"> "{{ pokemon.name }}" </p>
            <ul id="answer">  
              <li>Index number: {{ pokemon.id }} </li>
            <li>Type: {{ pokemon.types[0].type.name }}</li>
            <li>Height: {{ pokemon.height }}0 cm </li>
            <li>Weight: {{ pokemon.weight }} Hecto</li>
            
          </ul>
          </div> 
          <div class="SearchHere" v-else>
          <p>Dont know what you're looking for?</p>
          <p>Check out our <RouterLink class = "RouterLink" to="/list">List!</RouterLink></p>
        </div>
        </div>
      </div>
    </div>


</template>

<style scoped>

h1 {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
  margin-bottom: 5%; 
  font-family: 'Oswald', sans-serif;
  font-size: 5vh;

}
#SearchBar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right:20%;
  margin-left: 20%;
  margin-bottom: 10%;
  padding: 2vh;
  padding-bottom: 5%;
  background-color:antiquewhite;
  border-radius: 7px;
  border-color: black;
  border-style: double;
  border-width: 1vh;


}
.SearchHere {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  max-width: 350px;
  margin: auto;

}

#search {
margin-left: 30%;
margin-right: 30%;
margin-top:5%;
margin-bottom: 5%;
  padding: 10px;
  background-color:black;
  border-radius: 20px;
  color: white;
  font-size:100%;
  box-shadow: 10px 5px 5px #beb38b;
  cursor: pointer;
}

#title {
  margin-left: 10%;
  margin-right: 10%;
  padding: 10px;
  font-size: 17px;
  border-radius: 20px;
  color: rgb(8, 8, 8);
  border: 1px solid grey;
}
h2 {
display: flex;
justify-content: center;
align-items: center;
margin-bottom: 2vh;
font-family: 'Oswald', sans-serif;
font-size: 4vh;
}

p {
  font-family: sans-serif;
  font-size: 2vh;
  margin: 0%;
}
.info {
  text-align: center;
  font-size: 3vh;
}
.RouterLink {
  font-size: 2vh;
  font-family: sans-serif;
  margin:0% ;
}
.RouterLink:hover {
  text-decoration: underline;
}
#answerbox {
  background-color: white;
  margin: auto;
  padding: 10%;
  border-radius: 5px;
  box-shadow: 10px 5px 5px #beb38b;

}
#answer {
  margin-top: 3%;
  font-size: 3vh;
  list-style:circle;
}
#Sprite {
  margin: auto;
  height: 200%;
  width: 200%;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media  (max-width: 375px) {
  h1 {
font-size: 3vh;

  }
  #SearchBar {
   margin-left: 5%;
   margin-right: 2vh;
  }

  #answer {
    font-size: 2vh;
  }
}
</style>