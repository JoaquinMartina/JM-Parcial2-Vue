<template>
  <div class="alert alert-warning alert-dismissible fade show" role="alert">
    <h2>{{ gameSelected.nombre }}</h2>
    <p>
      Plataforma: <strong>{{ gameSelected.plataforma }}</strong>
    </p>
    <p>
      Estado: <strong>{{ gameSelected.estado }}</strong>
    </p>
    <p>
      Puntaje: <strong>{{ gameSelected.puntaje }}</strong>
    </p>
    <button
      type="button"
      class="btn-close"
      data-bs-dismiss="alert"
      aria-label="Close"
      @click="clearGame()"
    ></button>
  </div>
</template>

<script>
export default {
  name: "GameDetails",
  props: {
    gameSelected: {
      type: Object,
      required: true,
    },
  },
  methods: {
    clearGame() {
      this.$emit("clear-game");
    },
  },
};
</script>

<style scoped>
p {
  text-align: left;
}
</style>
