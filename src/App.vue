<template>
  <div id="app">
    <div id="inputs-container">
      <NumberInput
        v-for="(input, index) in inputs"
        :key="index"
        :defaultValue="input"
        v-model="inputs[index]"
      />
    </div>
    <button @click="addInput">{{total}}</button>
  </div>
</template>

<script>
import NumberInput from "./components/NumberInput.vue";

export default {
  name: "App",
  components: {
    NumberInput,
  },
  data: function () {
    return {
      inputs: [5, 10, 15, 20, 50],
    };
  },
  computed: {
    total() {
      return this.inputs.reduce((prev, current) => prev + current, 0);
    },
  },
  methods: {
    addInput() {
      this.inputs.push(this.getRandomInt(1, 10));
    },
    getRandomInt(min, max) {
      return Math.floor(Math.random() * (max - min) + min);
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#inputs-container {
  box-sizing: border-box;
  width: 100%;
  max-width: 322px;
  margin: 0 auto;
}
button {
  box-sizing: border-box;
  width: 100%;
  max-width: 322px;
  padding: 5px;
  font-weight: bold;
}
</style>
