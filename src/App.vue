<script setup>
  import { ref } from 'vue'
  
  const numero1 = ref(0)
  const numero2 = ref(0)
  const operacao = ref('')
  const calculo = ref(0)

  const realizarCalculo = () => {
    switch (operacao.value) {
      case 'somar':
        calculo.value = parseFloat(numero1.value) + parseFloat(numero2.value)
        break
      case 'subtrair':
        calculo.value = parseFloat(numero1.value) - parseFloat(numero2.value)
        break
      case 'multiplicar':
        calculo.value = parseFloat(numero1.value) * parseFloat(numero2.value)
        break
      case 'divisao':
        calculo.value = parseFloat(numero1.value) / parseFloat(numero2.value)
        break
      default:
        calculo.value = 0
        break
    }
  }

</script>
<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-warning rounded-3 border border-primary rounded">
      Calculadora aritmética
    </header>
    <div class="container">
      <div class="form-group">
        <label>Insira o primeiro número:</label>
        <input type="number" class="form-control mt-2" v-model="numero1">
        <label class="mt-5">Insira o segundo número:</label>
        <input type="number" class="form-control mt-2" v-model="numero2">
        <select class="form-control mt-5" v-model="operacao" @change="realizarCalculo">
          <option selected>Escolha o tipo de cálculo</option>
          <option value="somar">Somar</option>
          <option value="subtrair">Subtrair</option>
          <option value="multiplicar">Multiplicar</option>
          <option value="divisao">Divisão</option>
        </select>
        <h5 class="mt-5">Resultado: {{ calculo }}</h5>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .container header {
    text-align: center;
    font-size: 40px;
    font-weight: bold;
  }

  .form-group {
    width: fit-content;
    margin: 100px auto;
  }

  .form-group label {
    font-weight: bold;
  }

  input {
    max-width: 500px;
  }
</style>

