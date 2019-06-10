<template>
  <div id="app">
    <div class="left-nav">
      <img src="./assets/logo_giphy.gif">
      <li>
        <ul> <label for="search"><font-awesome-icon icon="coffee" /></label><GiphySearch :message="message"/></ul>
        <ul>Home</ul>
        <ul>Reactions</ul>
        <ul>Entertainment</ul>
        <ul>Sports</ul>
        <ul>Stickers</ul>
        <ul>Artists</ul>
      </li>
    </div>

  </div>
</template>

<script>
import GiphySearch from './components/GiphySearch.vue'

export default {
  name: 'app',
  components: {
    GiphySearch
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
  .left-nav{
    width: 15%;
    height: 100%;
    position: absolute;
    margin: 0 auto;
    box-shadow: 8px 0 10px -10px black;
  }
  .left-nav img {
    margin-top: 50px;
    width: 80%;
  }
  .left-nav li,ul{
    text-align: left;
    list-style-type: none;
    padding: 5px 10px;
  }
</style>
