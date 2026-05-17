<script>
export default {
  data() {
    return {
      count: 0,
      name: "vue",
    };
  },
  methods: {
    handleClick() {
      if (this.count % 2 == 0) {
        this.count = this.count + 2;
      } else {
        this.count = this.count - 2;
      }
    },
    greet(event) {
      alert(`Hello${this.name}!`);
      // `event` is the native DOM event
      if (event) {
        console.log(event);
        alert(event.target.tagName);
      }
    },
    handleSubmit() {
      console.log("Submit");
    },
  },
};
</script>

<template>
  <button v-on:click="handleClick">Count is:{{ count }}</button>
  <button @click="greet">Greet</button>

  <form v-on:submit.prevent="handleSubmit">
    <input type="text" />
    <button>Submit</button>
  </form>
</template>

<style></style>
