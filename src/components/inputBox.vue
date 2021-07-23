<template>
  <div>
    <input :type="type" v-model="input" :placeholder="placeholder" />
  </div>
</template>

<script>
export default {
  name: "inputBox",
  data() {
    return {
      input: "",
    };
  },
  props: {
    type: {
      type: String,
      default: () => "text",
    },
    placeholder: {
      type: String,
      default: () => "Please enter a value",
    },
    content: {
      type: String,
      default: () => "",
    },
  },

  methods: {
    update() {
      const payload = {
        content: this.content,
        value: this.input,
      };
      this.$emit("updateVal", payload);
    },
  },
  watch: {
    input(newval) {
      const payload = {
        content: this.content,
        value: newval,
      };
      this.$emit("updateVal", payload);
    },
  },
};
</script>