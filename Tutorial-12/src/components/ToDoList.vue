<template>
  <nav class="navbar">
    <h1>ToDo List</h1>
    <button @click="this.showModal = true">ADD</button>
  </nav>

  <main class="body">
    <TodoCard
      v-for="task in todo"
      :task="task"
      :key="task.id"
      @removeTask="(taskId) => removeTask(taskId)"
    />
  </main>

  <TaskModal
    v-if="showModal"
    @closeModal="showModal = false"
    @submitForm="(task) => addTask(task)"
  />
</template>

<script>
import TodoCard from "./TodoCard.vue";
import TaskModal from "./TaskModal.vue";

export default {
  components: {
    TodoCard,
    TaskModal,
  },

  data() {
    return {
      todo: [
        { id: 1, title: "Task - 1", description: "ABC" },
        { id: 2, title: "Task - 2", description: "ABC" },
        { id: 3, title: "Task - 3", description: "ABC" },
        { id: 4, title: "Task - 4", description: "ABC" },
      ],
      showModal: false,
    };
  },

  methods: {
    addTask(task) {
      const randomId = Math.floor(Math.random() * task.length);
      this.todo.push({
        id: randomId,
        title: task.title,
        description: task.description,
      });
      this.showModal = false;
    },

    removeTask(taskID) {
      this.todo = this.todo.filter((task) => task.id !== taskID);
    },
  },
};
</script>

<style>
.navbar {
  background-color: rgb(73, 115, 230);
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.header h1 {
  color: white;
  padding-left: 10px;
}
.header button {
  cursor: pointer;
  width: 70px;
  height: 40px;
  margin-right: 10px;
}

.body {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 30px;
  margin-top: 30px;
}
</style>
