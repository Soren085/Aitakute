<template>
  <h1>{{ msg }}</h1>
  <p>
    Ask a yes/no question:
    <input v-model="question" />
  </p>
  <p>{{ answer }}</p>
</template>

<script>
export default {
  name: "WatcherExample",

  props: {
    msg: String,
  },

  methods: {
    getAnswer() {
      this.answer = "Thinking...";
      axios
        .get("https://yesno.wtf/api")
        .then((res) => {
          this.answer = res.data.answer;
        })
        .catch((err) => {
          this.answer = "Error! " + error;
        });
    },
  },

  data() {
    return {
      question: "",
      answer: "Question needs a question mark",
    };
  },

  created() {},

  watch: {
    question(newQuestion, oldQuestion) {
      if (newQuestion.indexOf("?") > -1) {
        this.getAnswer();
      } else {
        this.answer = 'Question needs a question mark';
      }
    },
  },

  computed: {},
};
</script>
