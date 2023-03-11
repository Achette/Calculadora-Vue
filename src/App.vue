<template>
  <Calculator />
</template>

<script>
import Calculator from "./components/Calculator.vue";

export default {
  name: "App",
  components: {
    Calculator,
  },
};
</script>

<style>
* {
  outline: 0;
  font-family: "Open sans", sans-serif;
  box-sizing: border-box;
}

body {
  background: #1e293b;
  height: 100vh;
  margin: auto auto;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0;
  font-size: 1.3em;
  line-height: 1.5em;
}
</style>
