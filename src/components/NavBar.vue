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
    background: linear-gradient(180deg, #000000 50%, rgba(0,212,255,0) 50%);
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
      color: antiquewhite;
      margin: auto;
      position: absolute;
      top: 0;
      right: 5%;
    }

    .NavLink, .RouterLink {
      text-decoration: none;
      display: inline;
      color:antiquewhite;
      list-style-type: none;
      font-size: 7vh;
      font-family:fantasy;
      margin: 1vh;
    }
    li :hover {
      color: rgb(239, 184, 55);
      text-decoration:underline;
    }

    .logo {
      margin-bottom: 0%;
    }

  @media  (max-width: 375px) {

.RouterLink {
  font-size: 3vh;
}
  }
</style>
