<script>
export default {
  data() {
    return {
      question: "",
      answer: "Questions usually contain a question mark. ;-)",
      loading: false,
      form: {
        slug: "",
      },
    };
  },
  watch: {
    question(newQuestion, oldQuestion) {
      if (newQuestion.endsWith("?")) {
        this.getAnswers();
      }
    },
  },

  methods: {
    async getAnswers() {
      this.loading = true;
      this.answer = "Thinking...";
      try {
        const res = await fetch("https://yesno.wtf/api");
        this.answer = (await res.json()).answer;
      } catch (error) {
        this.answer = "Error! Could not reach the API. " + error;
      } finally {
        this.loading = false;
      }
    },
  },
};
</script>

<template>
  {{ form.slug }}
  <p>
    Ask a yes/no question:
    <input v-model="question" :disabled="loading" />
  </p>
  <p>{{ answer }}</p>
</template>
