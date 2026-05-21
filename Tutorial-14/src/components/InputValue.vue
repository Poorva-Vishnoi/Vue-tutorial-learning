<script>
export default {
  props: {
    labelValue: String,
    message: String,
  },

  emits: ["update-value"],
};
</script>

<template>
  <label>{{ labelValue }}</label>
  <input
    type="text"
    :value="message"
    @input="$emit('update-value', $event.target.value)"
  />
</template>
