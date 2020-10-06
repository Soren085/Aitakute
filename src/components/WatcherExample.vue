<template>
  <h1>{{ msg }}</h1>
  <!-- <p>
    Ask a yes/no question:
    <input v-model="question" />
  </p> -->
  <CustomInput @answer-change="answerChange"/>
  <Answer :answer="answer"/>
</template>

<script>
import Answer from './Answer.vue'
import CustomInput from './CustomInput.vue'

export default {
  name: "WatcherExample",
  components: {
    Answer,
    CustomInput
  },

  props: {
    msg: String,
  },

  methods: {
    answerChange(value) {
      this.answer = value;
    }
  },

  data() {
    return {
      answer: "Question needs a question mark",
    };
  },

  created() {},

  computed: {},
};
</script>
