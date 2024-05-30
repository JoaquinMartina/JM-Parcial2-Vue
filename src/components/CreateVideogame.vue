<template>
  <div class="divCreate">
    <h1>{{ title }}</h1>
    <form class="create">
      <input class="inputText" type="text" placeholder="Nombre" />
      <label>Plataforma</label>
      <select>
        <option value="pc">PC</option>
        <option value="pst">PlayStation</option>
        <option value="xbox">Xbox One</option>
      </select>
      <label>Estado</label>
      <select>
        <option value="pendiente">Pendiente</option>
        <option value="jugando">Jugando</option>
        <option value="completadp">Completado</option>
      </select>
      <input class="inputText" type="text" placeholder="Puntaje" /><br />
      <input class="btnRegistrar" type="submit" value="Registrar Videojuego" />
    </form>
  </div>
</template>

<script>
export default {
  name: "CreateVideogame",
  props: {
    title: String,
  },
};
</script>

<style scoped>
h1 {
  font-weight: bold;
}
label {
  display: inline-block;
  text-align: left;
  padding: 10px;
  margin: 10px;
  width: 100px;
}
select {
  display: inline-block;
  flex-direction: row;
  margin: 10px;
  padding: 5px;
  width: 110px;
  border-radius: 10px;
  border: 1px solid gray;
}
.divCreate {
  height: auto;
  display: flex;
  flex-direction: column;
  width: 500px;
  border-radius: 5px;
  padding: 20px;
  margin: 10px;
  margin-top: 30px;
  margin-bottom: 30px;
  background-color: rgb(245, 245, 245);
  border: 2px solid white;
}
.create {
  padding: 20px;
}
.inputText {
  display: inline-block;
  width: 250px;
  padding: 10px;
  margin: 10px;
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
  margin: 10px;
  padding: 10px;
  width: 250px;
  border: none;
}
</style>
