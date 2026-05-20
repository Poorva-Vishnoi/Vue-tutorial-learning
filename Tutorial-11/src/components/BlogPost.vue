<script>
export default {
  props: {
    // Multiple possible types
    // Required but nullable string
    title: {
      type: [String, null],
      required: true,
    },
    // Required string
    id: {
      type: Number,
      required: true,
    },
    // Number with a default value
    marks:{
      type: Number,
      default: 100,
    },
    isValid: Boolean,
    author: Object,
    tag: Array,
  },
  computed: {
    transform() {
      return this.title.toLowerCase();
    },
  },
};
</script>

<template>
  <h4>{{ id }} {{ title }} {{ isValid }}</h4>
  <h4>{{ author }}</h4>
  <h4>{{ tag }}</h4>
  <h4>{{ marks }}</h4>
</template>
