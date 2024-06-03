<template>
  <div class="divList">
    <h1>{{ title }}</h1>
    <div v-if="gameList.length == 0" class="alert alert-info" role="alert">
      <p>No hay Videojuegos para mostrar</p>
    </div>
    <table v-if="gameList.length != 0" class="table table-striped table-hover">
      <thead>
        <tr>
          <th v-for="field in fields" :key="field.id">
            {{ field }}
          </th>
        </tr>
      </thead>
      <tbody class="table-group-divider">
        <tr v-for="game in gameList" :key="game.id" @click="selectItem(game)">
          <td>{{ game.nombre }}</td>
          <td>{{ game.plataforma }}</td>
          <td>{{ game.estado }}</td>
          <td>{{ game.puntaje }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "ListVideogames",
  props: {
    title: String,
    gameList: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      fields: ["Nombre", "Plataforma", "Estado", "Puntaje"],
    };
  },
  methods: {
    selectItem(game) {
      this.$emit("game-detail", game);
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: bold;
}
.divList {
  padding: 20px;
  margin: 10px;
  background-color: rgb(245, 245, 245);
  border: 2px solid white;
  border-radius: 5px;
}
.inputText {
  display: inline-block;
  width: 100%;
  padding: 10px;
  margin: 10px;
  border: none;
  border-radius: 5px;
  background-color: rgb(253, 236, 255);
}
.btnRegistrar {
  color: white;
  background-color: rgb(22, 68, 82);
  text-align: center;
  font-size: medium;
  text-transform: uppercase;
  font-weight: bold;
  margin: 10px;
  padding: 10px;
  width: auto;
  border: none;
}
</style>
