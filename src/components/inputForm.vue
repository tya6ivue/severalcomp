<template>
  <div>
    <formData @clicked="clicked" :content="usersss" />
    <tableData />
  </div>
</template>
<script>
import formData from "./formData.vue";
import tableData from "./tableData.vue";

export default {
  name: "CustomInput",
  components: {
    formData,
    tableData,
  },
  data: function () {
    return {
      usersss: {},
    };
  },
  methods: {
    clicked(users) {
      console.log(users);
      this.usersss = users;
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