<template>
  <div>
    <h1>sdgt54yh</h1>
    <h1>{{ data.FirstName }}</h1>
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
    data: {
      type: Object,

      defaul: () => {},
    },
  },

  methods: {
    deleteItem: function (index) {
      this.todos.splice(index, 1);
    },
  },
};
