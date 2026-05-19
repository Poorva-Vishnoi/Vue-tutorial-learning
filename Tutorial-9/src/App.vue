<script>
import ApiTest from "./components/ApiTest.vue";
import DeepWatcher from "./components/deepWatcher.vue";
import EmailValidationEgUsingMethod from "./components/emailValidationEgUsingMethod.vue";
import EmailValidationUsingWatcher from "./components/emailValidationUsingWatcher.vue";
export default {
  components: {
    ApiTest,
    // EmailValidationEgUsingMethod,
    EmailValidationUsingWatcher,
    // DeepWatcher
  },
};
</script>

<template>
  <ApiTest />
  <!-- <EmailValidationEgUsingMethod/> -->
  <EmailValidationUsingWatcher/>
   <!-- <DeepWatcher/> -->
</template>

<style></style>
