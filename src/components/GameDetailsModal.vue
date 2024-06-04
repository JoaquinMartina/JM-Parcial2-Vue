<template>
  <div class="modal fade" id="gameDetails" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5">{{ gameSelected.nombre }}</h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <p>
            Plataforma: <strong>{{ gameSelected.plataforma }}</strong>
          </p>
          <p>
            Estado: <strong>{{ gameSelected.estado }}</strong>
          </p>
          <p>
            Puntaje: <strong>{{ gameSelected.puntaje }}</strong>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GameDetailsModal",
  props: {
    gameSelected: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: bold;
}
p {
  text-align: left;
}
</style>
