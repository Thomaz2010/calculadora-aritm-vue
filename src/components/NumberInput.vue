<template>
    <div class="form-group">
      <input 
        type="number" 
        class="form-control" 
        :value="value" 
        @input="$emit('update:value', $event.target.value)" 
        placeholder="Insira o número"
      />
    </div>
  </template>
  
  <script>
  export default {
    props: {
      value: {
        type: Number,
        required: true
      }
    }
  };
  </script>
  
  