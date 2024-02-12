<script>
export default {
  data() {
    return {
      pokemon: null
    }
  },
    created() {
      fetch('https://pokeapi.co/api/v2/pokemon/?offset=0&limit=151')
        .then((response) => response.json())
        .then((result) => {
          this.pokemon = result
        })
      },
    }
</script>

<template>
        <div id="PokeSum">
      <div>
        <h2> Pick from list</h2>
    <ul class="PokeList" v-if="pokemon !==null">
      <li  v-for="poke in pokemon.results" :key="poke.name">
        {{ poke.name }}
      </li>
    </ul>
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
  display: flex;  justify-content: center;
  align-items: center;
  margin:20vh;
  background-color: aliceblue;
  border-radius: 7px;
  border-color: black;
  border-style: double;
  border-width: 1vh;
  list-style-type: none;
  
 

}
li {
  display: inline-block;
  text-align: center;
  margin: 3vh;
  padding: 2vh;
  font-size: 1,5em;

}
</style>
