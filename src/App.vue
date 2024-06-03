<template>
  <nav>
    <router-link to="/"><img src="./assets/GamerZoneLogo.png" /></router-link>
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
  color: #2c3e50;
}

nav {
  background-color: #51a39f;
  padding: 20px;
  padding-left: 40px;
  display: flex;
  flex-direction: row;
  align-items: center;
}

img {
  width: 200px;
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
