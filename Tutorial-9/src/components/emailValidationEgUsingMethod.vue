<script>
export default {
  data() {
    return {
      form: {
        email: "",
      },
      message: "",
    };
  },

  methods: {
    validateEmail() {
      const regex = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

      if (regex.test(this.form.email)) {
        this.message = "Valid Email";
      } else {
        this.message = "Invalid Email";
      }
    },
  },
};
</script>

<template>
  <h3>Email Validation:</h3>
  {{ message }}
  <input type="text" v-model="form.email" @input="validateEmail"/>
</template>

<style></style>
