<script>
export default {
  data() {
    return {
      text: "",
    };
  },
};
</script>

<template>
    {{ text }}
  <input :value="text" @input="(event) => (text = event.target.value)" />
</template>

<style></style>
