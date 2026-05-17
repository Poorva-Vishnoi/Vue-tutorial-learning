<template>
  <div class="accordian">
    <header>
      <h3>title</h3>
      <button @click="toggleVisible">{{ isVisbile ? "-" : "+" }}</button>
    </header>
    <p class="content" :class="{ 'show-content': isVisbile }">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur
      exercitationem alias assumenda odio, harum at enim, omnis esse ratione
      necessitatibus recusandae laborum modi ipsum quis deleniti repellat,
      expedita quas id.
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return { isVisbile: false };
  },
  methods: {
    toggleVisible() {
      this.isVisbile = !this.isVisbile;
    },
  },
};
</script>

<style>
.accordian {
  width: 300px;
  margin: 40px 0px;
}
.accordian header {
  background-color: blueviolet;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}
header h3 {
  color: white;
}

header button {
  background-color: rgb(88, 114, 209);
  border: none;
  border: white solid 1px;
  padding: 5px 10px;
  font-size: 16px;
  cursor: pointer;
}

.accordian .content {
  display: none;
}

.accordian .show-content{
    display: block;
}

.abc{
  /* display: none; */
  background-color: red;
}
</style>
