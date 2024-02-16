<script>
export default {
  data() {
    return {
      pokemon: null
    }
  },
    methods: {
      fetchData() {
      fetch('https://pokeapi.co/api/v2/pokemon/?offset=0&limit=151')
        .then((response) => response.json())
        .then((result) => {
          this.pokemon = result;
          console.log(this.pokemon)
        })
      }
        },
        created() {
          this.fetchData();
        }
      }
      

</script>

<template>
      <div id="PokeSum">
      <div>
        <h2> Pokémon List</h2>
    <div class="PokeList" v-if="pokemon !==null">
      <ul  v-for="pokemon in pokemon.results" :key="pokemon" >
      <li class="Name">{{ pokemon.name }}</li> 
      <li class="info">Height: {{ pokemon.height }}0 cm </li>
      <li class="info">Weight: {{ pokemon.weight }} Hecto</li>
      <li class="info">Indexnumber: {{ pokemon.id }}</li> 
      </ul>
    </div>
    <div v-else>Loading...</div>
  </div>
    </div>
</template>

<style scoped>
h2 {
    font-size: 2vw;
    text-align: center;
    text-decoration: underline;
    
}
#PokeSum {
  display: flex;  
  justify-content: center;
  align-items: center;
  margin:10vh;
  background-color: aliceblue;
  border-radius: 7px;
  border-color: black;
  border-style: double;
  border-width: 1vh;
  list-style-type: none;
}
.Name {
  font-size: 3vh;
  text-decoration: underline;
}
li {
  display: inline-block;
  text-align: center;
  margin: 3vh;
  padding: 2vh;
  font-size: 1,5em;

}
#answer {
  margin-top: 3%;
  font-size: 25px;
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
  h2 {
font-size: 3vh;

  }
  #PokeSum {
   margin-left: 5%;
   margin-right: 5%;
  }
}
</style>
