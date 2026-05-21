<script>
import InputValue from "./components/InputValue.vue";
import InputValue2 from "./components/InputValue2.vue";

export default {
  components: {
    InputValue,InputValue2,
  },
  data() {
    return {
      message: "",
      first: '',
      last: ''
    };
  },
};
</script>

<template>
  {{ message }}
  <InputValue
    labelValue="Name"
    :message="message"
    @update-value="(value) => (message = value)"
  />

  <InputValue2
    v-model:firstName="first"
    v-model:lastName="last"
  />
  <p>{{ first }} {{ last }}</p>

</template>

<style></style>
