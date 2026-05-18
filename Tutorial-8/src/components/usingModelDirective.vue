<script>
export default {
  data() {
    return {
      form: {
        name: "",
        age: 0,
        message: "",
        checked: false,
        admins: [],
        radioNumber: null,
        role: null,
        pick: null,
      },
      fetchedFromAPI: [],
      firstPick: {
        name: "abc",
        age: 20,
      },
      secondPick: {
        name: "efg",
        age: 30,
      },
    };
  },
  methods: {
    tranformUppercase() {
      this.form.name = this.form.name.toUpperCase();
    },
    dynamicForm() {
      this.fetchedFromAPI = [
        { text: "one", value: "A" },
        { text: "Two", value: "B" },
        { text: "Three", value: "C" },
      ];
    },
  },
  mounted() {
    this.dynamicForm();
  },
};
</script>

<template>
  {{ form }}
  <p style="white-space: pre-line">{{ form.message }}</p>
  <br /><br /><br />
  <label>Name:</label>
  <input v-model="form.name" />
  <br /><br />
  <label>Age:</label>
  <input type="number" v-model="form.age" />
  <br /><br />
  <label>Message:</label>
  <textarea v-model="form.message"></textarea>
  <br /><br />
  <label>Checked</label>
  <input type="checkbox" v-model="form.checked" />
  <br /><br />
  <label>Admins:</label>
  <input type="checkbox" value="John" v-model="form.admins" />
  <label for="John">John</label>

  <input type="checkbox" value="Ron" v-model="form.admins" />
  <label for="Ron">Ron</label>

  <input type="checkbox" value="Jack" v-model="form.admins" />
  <label for="Jack">Jack</label>

  <br /><br />
  <label> Radio Number : </label>
  <label>
    Male
    <input type="radio" value="Male" v-model="form.radioNumber" />
  </label>
  <label>
    Female
    <input type="radio" value="Female" v-model="form.radioNumber" />
  </label>

  <br /><br />
  <label> Please select one </label>
  <select v-model="form.role">
    <option disabled value="">Please select one</option>
    <option>Frontend</option>
    <option>Backend</option>
    <option>Full Stack</option>
  </select>

  <br /><br />
  <label> Dynamic Form Role</label>
  <select v-model="form.role">
    <option v-for="data in fetchedFromAPI" :value="data.value">
      {{ data.text }}
    </option>
  </select>

  <br><br>
  <label>
    First Pick
    <input type="radio" :value="firstPick" v-model="form.pick" />
  </label>
  <label>
    Second Pick
    <input type="radio" :value="secondPick" v-model="form.pick" />
  </label>

  <!-- <button @click="tranformUppercase">Transform</button> -->
</template>

<style></style>
