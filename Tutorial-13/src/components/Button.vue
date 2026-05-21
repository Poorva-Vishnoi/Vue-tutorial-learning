<script>
export default {
  emits: ["onClick"],
  props: {},
};
</script>

<template>
  <button @click="$emit('onClick')">
    <slot></slot>
  </button>
</template>

<style></style>
