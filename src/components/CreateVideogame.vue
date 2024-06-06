<template>
  <div class="divCreate shadow-lg p-3 mb-5 bg-body-tertiary rounded">
    <h1>{{ title }}</h1>
    <div class="alert alert-danger" v-if="errorsForm.length">
      <ul>
        <li v-for="error in errorsForm" :key="error">
          <p>{{ error }}</p>
        </li>
      </ul>
    </div>
    <form @submit.prevent="addGame" class="">
      <div class="row mb-4">
        <label class="col-sm-3 col-form-label">Nombre</label>
        <div class="col-sm-8">
          <input class="form-control" type="text" v-model="nombre" />
        </div>
      </div>
      <div class="row mb-4">
        <label class="col-sm-3 col-form-label">Plataforma</label>
        <div class="col-sm-5">
          <select class="form-select" v-model="plataforma">
            <option value="PC">PC</option>
            <option value="PlayStation">PlayStation</option>
            <option value="Xbox One">Xbox One</option>
          </select>
        </div>
      </div>
      <div class="row mb-4">
        <label class="col-sm-3 col-form-label">Estado</label>
        <div class="col-sm-5">
          <select class="form-select" v-model="estado">
            <option value="Pendiente">Pendiente</option>
            <option value="Jugando">Jugando</option>
            <option value="Completado">Completado</option>
          </select>
        </div>
      </div>
      <div class="row mb-3">
        <label class="col-sm-3 col-form-label">Puntaje</label>
        <div class="col-sm-4">
          <input class="form-control" type="text" v-model="puntaje" />
        </div>
      </div>
      <div class="row mb-3">
        <label class="col-sm-3 col-form-label"></label>
        <div class="col-sm-8">
          <input
            class="btnRegistrar"
            type="submit"
            value="Registrar Videojuego"
          />
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "CreateVideogame",
  props: {
    title: String,
  },
  data() {
    return {
      nombre: null,
      plataforma: null,
      estado: null,
      puntaje: null,
      games: [],
      errorsForm: [],
    };
  },
  methods: {
    validateForm() {
      if (this.nombre === null) {
        this.errorsForm.push("Debe ingresar un nombre");
      }
      if (this.plataforma === null) {
        this.errorsForm.push("Debe elegir la plataforma");
      }
      if (this.estado === null) {
        this.errorsForm.push("Debe seleccionar el estado");
      }
      if (
        Number.isFinite(parseInt(this.puntaje)) == false &&
        (this.puntaje !== null || this.puntaje == "")
      ) {
        this.puntaje = null;
        this.errorsForm.push("El puntaje debe ser numérico");
      } else if (this.puntaje !== null && this.puntaje < 1) {
        this.puntaje = null;
        this.errorsForm.push("El puntaje debe ser como mínimo 1");
      } else if (this.puntaje !== null && this.puntaje > 10) {
        this.puntaje = null;
        this.errorsForm.push("El puntaje debe ser como máximo 10");
      }
    },
    addGame() {
      this.errorsForm = [];
      this.validateForm();
      if (this.errorsForm.length !== 0) {
        return;
      }
      const newGame = {
        nombre: this.nombre,
        plataforma: this.plataforma,
        estado: this.estado,
        puntaje: this.puntaje,
      };

      this.$emit("add-game", newGame);

      this.nombre = null;
      this.plataforma = null;
      this.estado = null;
      this.puntaje = null;
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: bold;
}
label {
  text-align: left;
}
form {
  margin: 30px;
}
p {
  text-align: left;
}
.divCreate {
  padding: 20px;
  margin-top: 10px;
  margin-bottom: 10px;
  background-color: rgb(245, 245, 245);
  border: 2px solid white;
  border-radius: 5px;
}
.inputText {
  padding: 10px;
  border: 1px solid gray;
  border-radius: 5px;
  background-color: white;
}
.btnRegistrar {
  color: white;
  background-color: rgb(22, 68, 82);
  text-align: center;
  font-size: medium;
  text-transform: uppercase;
  font-weight: bold;
  padding: 10px;
  width: 100%;
  border: none;
  border-radius: 5px;
}
</style>
