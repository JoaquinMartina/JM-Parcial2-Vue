<template>
  <nav>
    <router-link to="/">
      <img class="imgHeader" src="./assets/GamerZoneLogo.png" />
    </router-link>
  </nav>
  <router-view />
  <footer>
    <a href="https://github.com/JoaquinMartina/JM-Parcial2-Vue" target="_blank">
      <img class="imgFooter" src="./assets/GitHub.png" alt="GitHub" />
    </a>
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

.imgHeader {
  width: 200px;
}

.imgFooter {
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
  text-align: center;
}
</style>
