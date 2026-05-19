<script>
export default {
  data() {
    return {
      form: {
        email: "",
        slug: "",
      },
      message: "",
    };
  },

  watch: {
    "form.email"(newValue) {
      const regex =
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

      if (regex.test(newValue)) {
        this.message = "Valid Email";
        console.log("Valid Email");
      } else {
        this.message = "Invalid Email";
      }
    },

    "form.slug"(newValue) {
      this.form.slug = newValue.toLowerCase().replaceAll(" ", "-");
    },
  },
};
</script>

<template>
  {{ form.slug }}

  <input type="text" v-model="form.slug" />

  <h3>Email Validation:</h3>
  {{ message }}
  <input type="text" v-model="form.email" />
</template>

<style></style>
