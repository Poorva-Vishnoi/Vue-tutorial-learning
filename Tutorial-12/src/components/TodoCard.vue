<template>
  <div class="todo-card">
    <header class="card-header">
      <h4>{{ task.title }}</h4>
      <button @click="$emit('removeTask', task.id)">Remove</button>
    </header>
    <p>
      {{ task.description }}
    </p>
  </div>
</template>

<script>
export default {
  props: {
    task: Object,
  },

  emits: ["removeTask"], 
};
</script>

<style scoped>
.body {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 30px;
  margin-top: 30px;
}

.body .todo-card {
  border: 2px solid rgb(31, 156, 149);
  padding: 10px;
  border-radius: 10px;
  background-color: rgb(37, 186, 181);
}

.body .todo-card .card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.card-header h4 {
  font-weight: bold;
}

.card-header button {
  background-color: rgb(150, 0, 0);
  color: white;
}
</style>
