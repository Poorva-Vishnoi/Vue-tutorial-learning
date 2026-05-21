<script>
import Button from "./components/Button.vue";
import Card from "./components/Card.vue";
import DynamicComponent from "./components/DynamicComponent.vue";
import NamedSlot from "./components/NamedSlot.vue";

export default {
  components: {
    Button,
    NamedSlot,
    Card,
    DynamicComponent
  },

  data() {
    return {
      parentState: "I am the parent state",
    };
  },
};
</script>

<template>
  <!-- <Button>
    <span>{{ parentState }}</span>
    <img src="https://vuejs.org/assets/components.B1JZbf0_.png" width="150px" />
  </Button>

  <NamedSlot>
    <template v-slot:icon-left>
      <img src="https://vuejs.org/assets/components.B1JZbf0_.png" width="150px"
    /></template>
    <template v-slot:text> Save </template>
    <template v-slot:icon-right>
      <img src="https://vuejs.org/assets/components.B1JZbf0_.png" width="150px"
    /></template>
  </NamedSlot>
  <button @click="parentState = 'clicked'">Click Me</button>

  <Card/> -->

  <DynamicComponent/>
</template>

<style></style>
