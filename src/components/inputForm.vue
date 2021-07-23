<template>
  <div>
    <formData @clicked="clicked" />
    <tableData :content="form_values" />
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
      form_values: {},
    };
  },
  methods: {
    clicked(users) {
      // console.log(users);
      this.form_values =  users;
    },
  },
  watch: {
    form_values: function(old, newval) {
      console.log(old, newval)
    }
  }
};
</script>
<style scoped>


.btn {
  margin-right: 5px;
  margin-left: 10px;
}
.buttonn {
  margin-top: 20px;
  width: 200px;
}
</style>