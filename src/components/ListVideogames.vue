<template>
  <div class="divList">
    <h1>{{ title }}</h1>
    <table class="table table-striped table-hover">
      <thead>
        <tr>
          <th v-for="field in fields" :key="field.id">
            {{ field }}
          </th>
        </tr>
      </thead>
      <tbody class="table-group-divider">
        <tr v-for="item in items" :key="item.id">
          <td>{{ item.first_name }}</td>
          <td>{{ item.last_name }}</td>
          <td>{{ item.age }}</td>
          <td>5</td>
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
  },
  data() {
    return {
      fields: ["first_name", "last_name", "age"],
      items: [
        {
          isActive: true,
          age: 40,
          first_name: "Dickerson",
          last_name: "Macdonald",
        },
        {
          isActive: false,
          age: 21,
          first_name: "Larsen",
          last_name: "Shaw",
        },
        {
          isActive: false,
          age: 89,
          first_name: "Geneva",
          last_name: "Wilson",
        },
        {
          isActive: true,
          age: 38,
          first_name: "Jami",
          last_name: "Carney",
        },
      ],
    };
  },
};
</script>

<style scoped>
h1 {
  font-weight: bold;
}
.divList {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  border-radius: 5px;
  padding: 20px;
  margin: 10px;
  margin-top: 30px;
  margin-bottom: 30px;
  background-color: rgb(197, 197, 197);
  border: 2px solid white;
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
