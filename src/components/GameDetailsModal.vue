<template>
  <div class="modal fade" id="gameDetailModal" aria-hidden="false">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5"></h1>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <p>Plataforma:</p>
          <p>Estado:</p>
          <p>Puntaje:</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GameDetailsModal",
  props: {
    gameSelectedModal: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
p {
  text-align: left;
}
</style>
