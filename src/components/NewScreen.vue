<template>
  <h1>{{ msg }}</h1>
  <p>{{ publishedAge }}</p>
  <button v-on:click="animalUpdate()">update</button>
</template>

<script>
export default {
  name: "NewScreen",

  props: {
    msg: String,
  },

  methods: {
    animalUpdate() {
      this.animal.age > 0 ? this.animal.age-- : this.animal.age = 0;
    },
  },

  data() {
    return {
      animal: {
        name: "cat",
        age: 2
      },
      food: {
        name: 'mango',
        age: 3
      }
    };
  },

  created() {
    // `this` points to the vm instance
    console.log("age is: " + this.animal.age);
  },

  computed: {
    // a computed getter
    publishedAge() {
      // `this` points to the vm instance
      return this.animal.age + this.food.age;
    }
  }

};
</script>
