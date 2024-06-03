<template>
  <div class="divSearch">
    <input
      class="form-control"
      type="text"
      v-model="value"
      placeholder="Buscar"
      @input="filterResults(value)"
    />
  </div>
</template>

<script>
export default {
  name: "GameSearch",
  data() {
    return {
      value: "",
    };
  },
  methods: {
    filterResults(value) {
      this.$emit("game-search", value);
    },
  },
};
</script>

<style scoped>
.divSearch {
  padding: 20px;
  margin: 10px;
  background-color: rgb(245, 245, 245);
  border: 2px solid white;
  border-radius: 5px;
}
</style>
