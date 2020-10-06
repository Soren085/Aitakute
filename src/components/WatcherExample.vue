<template>
  <h1>{{ msg }}</h1>
  <custom-input @answer-change="answerChange"/>
  <answer-detail :answer="answer"/>
</template>

<script>
import Answer from './Answer.vue'
import CustomInput from './CustomInput.vue'

export default {
  name: "WatcherExample",
  components: {
    'answer-detail': Answer,
    'custom-input': CustomInput
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
