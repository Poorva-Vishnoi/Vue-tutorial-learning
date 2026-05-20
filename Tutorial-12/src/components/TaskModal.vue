<script>
export default {
  emits: ["closeModal", "submitForm"],

  data() {
    return {
      Form: {
        title: "",
        description: "",
      },
    };
  },
  
  methods:{
    sumbitForm(){
       this.$emit("submitForm", this.Form); 
    }
  }
};
</script>
<template>
  <div class="modal-wrapper">
    <div class="modal-bg"></div>
    <div class="modal">
      <header>
        <h4>ADD TASK</h4>
        <button @click="$emit('closeModal')">X</button>
      </header>
      <label for="">
        Title
        <input type="text" placeholder="Enter title" v-model="Form.title" />
      </label>
      <label>
        Description
        <textarea
          placeholder="Enter description"
          v-model="Form.description"
        ></textarea>
      </label>
      <footer>
        <button @click="$emit('closeModal')">Cancel</button>
        <button @click="sumbitForm">ADD</button>
      </footer>
    </div>
  </div>
</template>

<style scoped>
.modal-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  /* display: none; */
}

.modal-wrapper .modal-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: -1;
}

.modal-wrapper .modal {
  background-color: white;
  padding: 10px 20px;
  border-radius: 10px;
  width: 100%;
  max-width: 450px;
}

.modal-wrapper .modal header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.modal-wrapper .modal header h4 {
  font-weight: bold;
}

.modal-wrapper .modal label {
  display: block;
}

.modal-wrapper .modal label input,
.modal-wrapper .modal label textarea {
  width: 100%;
  margin-bottom: 10px;
}

.modal-wrapper .modal footer {
  margin-top: 10px;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 30px;
}
</style>
