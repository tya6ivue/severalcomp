<template>
  <div>

    <button>{{myName}}</button>
    <FormData  />
    
    <table>
      <tr v-for="(todo, index) in todos" :key="index">
        <td>{{ todo.id }}</td>
        <td>{{ todo.FirstName }}</td>
        <td>{{ todo.LastName }}</td>
        <td>{{ todo.MobileNumber }}</td>
        <td>{{ todo.Email }}</td>
        <td>{{ todo.Address }}</td>
        <td><button class="btn" v-on:click="deleteItem(index)">X</button></td>
      </tr>
    </table>
  </div>
</template>
<script>
import FormData from './FormData.vue'
export default {
  name: "CustomInput",
  components: {
  FormData
  },
  data: function () {
    return {
      todos: [
        {
          id: 1,
          FirstName: "Kurtis",
          LastName: "Weisslnat",
          MobileNumber: "+91********",
          Email: "xyz@gmail.com",
          Address: "Rex Trails",
        },
        {
          id: 2,
          FirstName: "Earvin",
          LastName: "Graham",
          MobileNumber: "+91********",
          Email: "xyz@gmail.com",
          Address: "Victor",
        },
        {
          id: 3,
          FirstName: "Patrica",
          LastName: "Chelse",
          MobileNumber: "+91********",
          Email: "xyz@gmail.com",
          Address: "Sliks walls",
        },
      ],
      address: "",
      firstName: "",
      lastName: "",
      eMial: "",
      MobileNumber: "",
    };
  },
  methods: {
    addItem: function () {
      if (
        this.address === "" ||
        this.firstName === null ||
        this.MobileNumber === "" ||
        this.eMial === "" ||
        this.lastName.value === 0
      ) {
        alert("Please fill input value");
        return false;
      }

      this.todos.push({
        id: Math.floor(Math.random() * 100),
        FirstName: this.firstName,
        LastName: this.lastName,
        MobileNumber: this.mobileNumber,
        Email: this.eMial,
        Address: this.address,
      });

      (this.firstName = ""),
        (this.lastName = ""),
        (this.address = ""),
        (this.eMial = ""),
        (this.mobileNumber = "");
    },
    deleteItem: function (index) {
      this.todos.splice(index, 1);
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

.btn {
  margin-right: 5px;
  margin-left: 10px;
}
.buttonn {
  margin-top: 20px;
  width: 200px;
}
</style>