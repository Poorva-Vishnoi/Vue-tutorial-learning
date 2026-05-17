<script>
// import Counter from "./components/Counter.vue";
import Accordian from "./components/Accordian.vue";
export default {
  components: {
    // Counter
    Accordian,
  },
  data() {
    return {
      isActive: true,
      //normal way to bind styles
      color: "red",
      fontSize: '20',
      //good idea to bind to a style object directly so that the template is cleaner
      styleObject: {
        color: "red",
        fontSize: '20'
      },
    }
  },
}
</script>

<template>
  <Accordian :class="{ abc: isActive }" />
  <div :style="styleObject">Testing</div>
</template>

<style scoped></style>
