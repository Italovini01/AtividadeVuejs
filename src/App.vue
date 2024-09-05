<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    
    <div class="calculator">
      <input type="number" v-model.number="number1" placeholder="Primeiro número" />
      
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      
      <input type="number" v-model.number="number2" placeholder="Segundo número" />
      
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add'
    }
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
}
</script>

<style>
    /* Estilização Geral
    body {
        background-color: #f4f4f9;
        font-family: 'Arial', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
    }
    
    /* Contt Calculadora */
    .calculator {
        background-color: #ffffff;
        padding: 30px;
        border-radius: 15px;
        box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 400px;
        width: 100%;
    }
    
    /* estilizando o  Título */
    h1 {
        font-size: 24px;
        color: #333333;
        margin-bottom: 20px;
        text-align: center;
    }
    
    /* Estilo dos inputs e selects */
    input[type="number"], select {
        width: 100%;
        padding: 15px;
        margin: 10px 0;
        border: 2px solid #ddd;
        border-radius: 10px;
        font-size: 16px;
        box-sizing: border-box;
        transition: border-color 0.3s;
    }
    
    /* Efeito ao focar nos campos */
    input[type="number"]:focus, select:focus {
        border-color: #007BFF;
        outline: none;
    }
    
    /* Estilo do select */
    select {
        appearance: none;
        background-color: #fff;
        cursor: pointer;
    }
    
    /* Indicador de seta no select */
    select {
        background-image: url('data:image/svg+xml;charset=US-ASCII,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 4 5"><path fill="none" stroke="%23007BFF" stroke-width="1px" d="M0 0l2 2 2-2"/></svg>');
        background-repeat: no-repeat;
        background-position: right 15px top 50%;
        background-size: 10px 10px;
    }
    
    /* Estilizando o  texto dos resultados */
    p {
        margin-top: 20px;
        font-size: 28px;
        color: #007BFF;
        font-weight: bold;
        text-align: center;
        min-height: 40px; /* Layout não se altere ao exibir o resultado */
    }
    
    /* Responsividade */
    @media (max-width: 600px) {
        .calculator {
        padding: 20px;
        }
    
        h1 {
        font-size: 20px;
        }
    
        input[type="number"], select {
        font-size: 14px;
        padding: 10px;
        }
    
        p {
        font-size: 24px;
        }
    }
</style>
