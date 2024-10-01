
<template>
    <div class="form-group">
      <select class="form-control" :value="selectedOperator" @change="onOperatorChange">
        <option value="+">Adicionar</option>
        <option value="-">Subtrair</option>
        <option value="*">Multiplicar</option>
        <option value="/">Dividir</option>
      </select>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      selectedOperator: {
        type: String,
        required: true
      }
    },
    methods: {
      onOperatorChange(event) {
        
        this.$emit('update:operator', event.target.value);
      }
    }
  };
  </script>
  

  