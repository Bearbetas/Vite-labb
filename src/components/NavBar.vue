<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
  <nav class = "NavBar">
      <img  class="logo" src="../assets/img/pokelogo.png" alt="pokelogo">
      <ul class="NavList">
        <li class="NavLink"><RouterLink class = "RouterLink" to="/">Home</RouterLink></li>
        <li class="NavLink"><RouterLink class = "RouterLink" to="/list">List</RouterLink></li>
      </ul>
    </nav>
  </header>

  <RouterView />
</template>

<style>
  nav {
      position: sticky;
      height: 100%;
      width: 100%;
      margin: 0%;
    }
    img{
      max-width: 50%;
      height: auto;
      }
    .NavList {
      margin: auto;
      position: absolute;
      top: 0;
      right: 5%;
    }

    .NavLink, .RouterLink {
      text-decoration: none;
      display: inline;
      color: #000000;
      list-style-type: none;
      font-size: 5vh;
      font-family: monospace;
      margin: 1em;
    }
    li :hover {
      color: rgb(76, 85, 82);
    }

    .logo {
      margin-bottom: 0%;
    }
</style>
