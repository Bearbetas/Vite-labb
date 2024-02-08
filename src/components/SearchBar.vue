
<template>
      <div id="SearchBar">
      <div id="searchbox">
        <h2>Who's that Pokémon?</h2>
        <div class="SearchHere">
          <input id="title" placeholder="Enter Pokémon" />
          <input id="search" type="button" value="Search" />
        </div>
        <p id="searchResults"></p>
      </div>
    </div>
</template>

<style>

h2 {

  margin-bottom: 2vh;
  font-family: 'Oswald', sans-serif;
  font-size: 5vh;

}
#SearchBar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin:20vh;
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
