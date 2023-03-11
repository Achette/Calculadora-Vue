<template>
  <section class="container">
    <h1>VueCalc-JS</h1>

    <table class="calculator">
      <tr>
        <td v-if="!result && !expression" colspan="4">
          <input type="text" class="display" v-model="display" />
        </td>
        <td v-else-if="!result" colspan="4">
          <input type="text" class="display" v-model="expression" />
        </td>
        <td v-else colspan="4">
          <input type="text" class="display" v-model="result" />
        </td>
      </tr>

      <tr>
        <td>
          <button @click="handleClear()" class="btn btn-clear">C</button>
        </td>
        <td>
          <button @click="handleClick('(')" class="btne btn-num">(</button>
        </td>
        <td>
          <button @click="handleClick(')')" class="btne btn-num">)</button>
        </td>
        <td>
          <button @click="handleClick('/')" class="btns btn-num">/</button>
        </td>
      </tr>

      <tr>
        <td><button @click="handleClick(7)" class="btn btn-num">7</button></td>
        <td><button @click="handleClick(8)" class="btn btn-num">8</button></td>
        <td><button @click="handleClick(9)" class="btn btn-num">9</button></td>
        <td>
          <button @click="handleClick('*')" class="btns btn-num">*</button>
        </td>
      </tr>

      <tr>
        <td><button @click="handleClick(4)" class="btn btn-num">4</button></td>
        <td><button @click="handleClick(5)" class="btn btn-num">5</button></td>
        <td><button @click="handleClick(6)" class="btn btn-num">6</button></td>
        <td>
          <button @click="handleClick('+')" class="btns btn-num">+</button>
        </td>
      </tr>

      <tr>
        <td><button @click="handleClick(1)" class="btn btn-num">1</button></td>
        <td><button @click="handleClick(2)" class="btn btn-num">2</button></td>
        <td><button @click="handleClick(3)" class="btn btn-num">3</button></td>
        <td>
          <button @click="handleClick('-')" class="btns btn-num">-</button>
        </td>
      </tr>

      <tr>
        <td>
          <button @click="handleClick('.')" class="btne btn-num">.</button>
        </td>
        <td><button @click="handleClick(0)" class="btn btn-num">0</button></td>
        <td>
          <button @click="handleDelete()" class="btne btn-del">&laquo;</button>
        </td>
        <td><button @click="handleCalcNow()" class="btn btn-eq">=</button></td>
      </tr>
    </table>
  </section>
</template>

<script>
export default {
  name: "Calculator-app",
  data() {
    return {
      display: "0",
      expression: "",
      result: "",
    };
  },
  methods: {
    handleClick(value) {
      this.expression = this.expression += value;
    },

    handleCalcNow() {
      let calc = String(this.expression);
      this.result = eval(calc);
    },

    handleClear() {
      this.expression = "";
      this.result = "";
    },

    handleDelete() {
      this.expression = this.expression.slice(0, -1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.container {
  max-width: 440px;
  margin: auto auto;
  background-color: #0f172a;
  padding: 20px;
  border-radius: 10px;
  border: 2px solid #1e3a8a;
  color: white;
}

.calculator {
  width: 18.75rem;
  background-color: #0f172a;
  margin: auto;
  border: 1px solid #1e3a8a;
  border-radius: 0.3rem;
  padding: 0.15em;
}

h1 {
  font-size: 1rem;
}

.display {
  font-size: 2em;
  width: 100%;
  text-align: right;
  background-color: #1e293b;
  color: #fff;
  border: none;
  margin: 0.5rem 0 0.5rem 0;
  border-radius: 0.625rem;
}

.btn,
.btns,
.btne {
  color: #fff;
  width: 5.25rem;
  height: 50px;
  font-size: 1.25em;
  border: none;
  background: #1e293b;
  cursor: pointer;
  border-radius: 0.625rem;
  font-weight: bold;
}

.btn:hover,
.btns:hover,
.btne:hover {
  background-color: #334155;
  border: 1px solid #3b82f6;
  color: #3b82f6;
}

.btn-eq {
  background-color: #1d4ed8;
  font-weight: bold;
}

.btn-eq:hover {
  background-color: #1e40af;
  border: 1px solid #3b82f6;
  color: #fff;
}
</style>
