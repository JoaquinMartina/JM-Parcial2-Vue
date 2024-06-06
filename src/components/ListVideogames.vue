<template>
  <div class="divList shadow-lg p-3 mb-5 bg-body-tertiary rounded">
    <h1>{{ title }}</h1>
    <div class="divSearch">
      <input
        class="form-control"
        type="text"
        v-model="buscar"
        placeholder="Buscar por nombre, plataforma o estado"
      />
    </div>
    <div v-if="gameList.length == 0" class="alert alert-info" role="alert">
      <p>No hay Videojuegos para mostrar</p>
    </div>
    <div class="collapse1">
      <table
        v-if="gameList.length"
        class="table table-striped table-hover table-borderless"
      >
        <thead>
          <tr>
            <th v-for="field in fields" :key="field.id">
              {{ field }}
            </th>
          </tr>
        </thead>
        <tbody class="table-group-divider">
          <tr
            v-for="game in games"
            :key="game.nombre"
            @click="selectItem(game)"
            data-bs-toggle="modal"
            data-bs-target="#gameDetails"
          >
            <td>{{ game.nombre }}</td>
            <td>{{ game.plataforma }}</td>
            <td>{{ game.estado }}</td>
            <td>{{ game.puntaje }}</td>
          </tr>
        </tbody>
      </table>
    </div>
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
      buscar: "",
    };
  },
  methods: {
    selectItem(game) {
      this.$emit("game-detail", game);
    },
  },
  computed: {
    games() {
      return this.gameList.filter((item) => {
        return (
          item.nombre.toLowerCase().includes(this.buscar.toLowerCase()) ||
          item.plataforma.toLowerCase().includes(this.buscar.toLowerCase()) ||
          item.estado.toLowerCase().includes(this.buscar.toLowerCase())
        );
      });
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
  margin-top: 10px;
  margin-bottom: 10px;
  background-color: rgb(245, 245, 245);
  border: 2px solid white;
  border-radius: 5px;
}
.divSearch {
  margin-bottom: 20px;
}
.collapse1 {
  overflow-y: scroll;
  height: 200px;
}
</style>
