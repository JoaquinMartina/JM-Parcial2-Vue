<template>
  <nav>
    <router-link to="/"><img src="./assets/GameZoneLogo.png" /></router-link>
  </nav>
  <router-view />
  <footer>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </footer>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  background-color: #51a39f;
  padding-left: 20px;
  padding-right: 20px;
  display: flex;
  flex-direction: row;
  text-align: center;
  align-items: center;
}

img {
  width: 150px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

footer {
  height: 150px;
  background-color: #51a39f;
  padding: 30px;
  display: flex;
  flex-direction: row;
  text-align: center;
}
</style>
