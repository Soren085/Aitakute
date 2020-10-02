<template>
  <h1>{{ msg }}</h1>
  Counter:
  <h1>{{ counter }}</h1>
  <!-- <button @click="mounted">count is: {{ count }}</button> -->
  <span v-bind:title="message">
    Hover your mouse over me for a few seconds to see my dynamically bound
    title!
  </span>
  <div id="event-handling">
    <p>{{ message }}</p>
    <button v-on:click="reverseMessage">Reverse Message</button>
  </div>
  <div id="two-way-binding">
    <input v-model="message" />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    counter: Number,
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split("").reverse().join("");
    },
  },
  data() {
    return {
      message: "You loaded this page on " + new Date().toLocaleString(),
    };
  },
};
</script>
