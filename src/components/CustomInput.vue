<template>
  <p>
    Ask a yes/no question:
    <input v-model="question" />
  </p>
</template>

<script>
export default {
  name: "CustomInput",

  props: {},

  methods: {
    getAnswer() {
      this.$emit("answer-change", "Thinking...");
      axios
        .get("https://yesno.wtf/api")
        .then((res) => {
          this.$emit("answer-change", res.data.answer);
        })
        .catch((err) => {
          this.$emit("answer-change", "Error! " + err);
        });
    },
  },

  data() {
    return {
      question: "",
    };
  },

  created() {},

  watch: {
    question(newQuestion, oldQuestion) {
      if (newQuestion.indexOf("?") > -1) {
        this.getAnswer();
      } else {
        this.$emit("answer-change", "Question needs a question mark");
      }
    },
  },

  computed: {},
};
</script>
