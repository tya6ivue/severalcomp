<template>
  <div>
    <table>
      <tr v-for="(jsonData, index) in myJson" :key="index">
        <td>{{ jsonData.id }}</td>
        <td>{{ jsonData.FirstName }}</td>
        <td>{{ jsonData.LastName }}</td>
        <td>{{ jsonData.MobileNumber }}</td>
        <td>{{ jsonData.Email }}</td>
        <td>{{ jsonData.Address }}</td>

        <td><button class="btn" v-on:click="deleteItem(index)">X</button></td>
      </tr>
      <tr>
        <td>xvrgwth{{ content }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import tableValue from "../jsonFile/tableValue.json";

export default {
  name: "tableData",

  data() {
    return {
      myJson: tableValue,
    };
  },
  props: {
    content: {
      type: Object,
      default: () => {},
    },
  },

  methods: {
    deleteItem: function (index) {
      this.todos.splice(index, 1);
      this.myJson = this.content;
    },
  },
};
</script>

<style scoped>
table {
  margin-top: 20px;
  width: 100%;
  background-color: yellow;
  border: 1px solid black;
}

table tr {
  padding: 10px;
  color: red;
}

table tr td {
  border: 1px solid black;
}
</style>