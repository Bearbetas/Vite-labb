<script setup>
//Importera navbar
import NavBar from './components/NavBar.vue'
import SearchBar from './components/SearchBar.vue'
import PokeList from './components/PokeList.vue';
</script>

<template>
  <header>
    <!-- Lägg in navbar komponent -->
    <NavBar />
  </header>
  <SearchBar />

  <PokeList />

</template>

<style scoped>


</style>
