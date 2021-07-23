<template>
  <div>
    <form class="form" name="myForm">
      First Name:<inputBox
        :type="'text'"
        :placeholder="'Enter First Name'"
        :content="'First_name'"
        @updateVal="updateVal"
      />
      Last Name:<inputBox
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

      <button class="button" type="submit" v-on:click.prevent="submit">Add</button>
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
    return {
      users: {
        id: "",
        FirstName: "",
        LastName: "",
        MobileNumber: "",
        Email: "",
        Address: "",
      },

      profileObj: {},
    };
  },
  methods: {
    updateVal(param) {
      if (param.content === "First_name") {
        this.users.FirstName = param.value;
      }

      if (param.content === "Last_name") {
        this.users.LastName = param.value;
      }
      if (param.content === "Mobile_number") {
        this.users.MobileNumber = param.value;
      }
      if (param.content === "Email-id") {
        this.users.Email = param.value;
      }
      if (param.content === "Address") {
        this.users.Address = param.value;
      }
    },
    submit() {
      this.$emit("clicked", this.users);
    },
  },
};
</script>

<style scoped>
.button {
  margin-top: 20px;
  width: 200px;
}
</style>