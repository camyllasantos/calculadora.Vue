<template>
  <div id="app">
    <h1>Calculadora</h1>

    <input type="number" v-model="numero1" placeholder="Número 1" />
    <input type="number" v-model="numero2" placeholder="Número 2" />

    <select v-model="operacao">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>

    <p>Resultado: {{ resultado }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
    };
  },
  computed: {
    resultado() {
      const num1 = parseFloat(this.numero1);
      const num2 = parseFloat(this.numero2);
      
      switch (this.operacao) {
        case 'soma':
          return num1 + num2;
        case 'subtracao':
          return num1 - num2;
        case 'multiplicacao':
          return num1 * num2;
        case 'divisao':
          return num2 !== 0 ? num1 / num2 : 'Divisão por zero!';
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

input {
  margin: 10px;
  padding: 5px;
  font-size: 18px;
}

select {
  margin: 10px;
  padding: 5px;
  font-size: 18px;
}

p {
  font-size: 24px;
  font-weight: bold;
}
</style>

