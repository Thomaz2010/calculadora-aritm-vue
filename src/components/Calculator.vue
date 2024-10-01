
<template>
    <div class="container">
      <h1 class="text-center p-5">Calculadora</h1>
  
     
      <select v-model="operator" class="form-control-sm mb-3">
        <option value="+">Adicionar</option>
        <option value="-">Subtrair</option>
        <option value="*">Multiplicar</option>
        <option value="/">Dividir</option>
      </select>
  
      
      <input type="number" v-model.number="number1" class="form-control mb-2" placeholder="Número 1" />
      <input type="number" v-model.number="number2" class="form-control mb-2" placeholder="Número 2" />
  
      
      <button class="btn btn-secondary mb-3" @click="clear">Limpar Tela</button>
  
     
      <h3> <b>Resultado:</b> {{ result }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        number1: 0,
        number2: 0,
        operator: '+'
      };
    },
    computed: {
      result() {
        // Cálculo do resultado baseado nos números e operador
        const n1 = parseFloat(this.number1);
        const n2 = parseFloat(this.number2);
  
        if (isNaN(n1) || isNaN(n2)) {
          return 'Insira números válidos';
        }
  
        if (this.operator === '+') return n1 + n2;
        if (this.operator === '-') return n1 - n2;
        if (this.operator === '*') return n1 * n2;
        if (this.operator === '/') return n2 !== 0 ? n1 / n2 : 'Erro: divisão por zero';
  
        return 0; // Valor padrão
      }
    },
    methods: {
      clear() {
        // Método para limpar os campos
        this.number1 = 0;
        this.number2 = 0;
        this.operator = '+';
      }
    }
  };
  </script>
  
  <style scoped>
  </style>
  