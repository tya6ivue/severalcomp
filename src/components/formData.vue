<template>
  <div>
    <form class="form" name="myForm">
      First Name:
      <inputBox
        :type="'text'"
        :placeholder="'Enter First Name'"
        :content="'First_name'"
        @updateVal="updateVal"
      />

      Last Name:
      <inputBox
        :type="'text'"
        :placeholder="'Enter Last Name'"
        :content="'Last_name'"
        @updateVal="updateVal"
      />
      Mobile number:
      <inputBox
        type="'tel'"
        :placeholder="'Enter Mobile Number'"
        :content="'Mobile_number'"
        name="phone"
        pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"
        @updateVal="updateVal"
      />

      Email:
      <inputBox
        :placeholder="'Enter Email id'"
        :content="'Email-id'"
        @updateVal="updateVal"
      />

      Address:
      <inputBox
        :placeholder="'Enter Address'"
        :content="'Address'"
        @updateVal="updateVal"
      />

      <button type="submit" @click.prevent="submit" class="button">Add</button>
    </form>
  </div>
</template>

<script>
import inputBox from "./inputBox.vue";
export default {
  name: "FormaData",
  components: {
    inputBox,
  },
  data() {
    this.param = 'someValue'
    return {
      
      profileObj: {},
    };
  },
  methods: {
    updateVal(param) {
      console.log(param);
    },
  
  },
  submit() {
    this.$emit('clicked', 'someValue')
  },
};
</script>

<style scoped>
.button {
  margin-top: 20px;
  width: 200px;
}
</style>