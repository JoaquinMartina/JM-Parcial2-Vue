<template>
  <div class="home">
    <CreateVideogame title="Nuevo Videojuego" />
    <ListVideogames title="Videojuegos" />
  </div>
</template>

<script>
import CreateVideogame from "@/components/CreateVideogame.vue";
import ListVideogames from "@/components/ListVideogames.vue";

export default {
  name: "HomeView",
  components: {
    CreateVideogame,
    ListVideogames,
  },
};
</script>

<style scoped>
.home {
  height: auto;
  display: flex;
  background-color: rgb(197, 197, 197);
}
</style>
