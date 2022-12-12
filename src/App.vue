<template>
  <div id="app">
    <h1>Calculator</h1>
    <div>
      <input type="text" v-model="input" />
      <br />
      <button v-for="op in operators" :key="op.i" @click="updateInput(op)">{{op}}</button>
    </div>
    <br />
    <div>
      <button v-on:click="calculate()">=</button>
    </div>
    <br />
    <div>
      Result: {{ result }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      input: '',
      result: '',
      operators: ['+', '-', '*', '/']
    }
  },
  methods: {
    updateInput(op) {
      this.input += op;
    },
    calculate() {
      this.result = eval(this.input);
    }
  }
}
</script>
