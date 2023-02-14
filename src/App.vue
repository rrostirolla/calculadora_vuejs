<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';

  const estado = reactive({
    numero1: '',
    numero2: '',
    operacao: 'default',
  })

  const calcula = () => {
    const { operacao } = estado;

    switch (operacao) {
      case 'soma':
        return soma();
      case 'subtrair':
        return subtracao();
      case 'multiplicar':
        return multiplicacao();
      case 'dividir':
        return divisao();
      default:
        return ''
    }
  }

  const soma = () => {
    return parseFloat(estado.numero1) + parseFloat(estado.numero2)
  }

  const subtracao = () => {
    return parseFloat(estado.numero1) - parseFloat(estado.numero2)
  }

  const multiplicacao = () => {
    return parseFloat(estado.numero1) * parseFloat(estado.numero2)
  }

  const divisao = () => {
    return parseFloat(estado.numero1) / parseFloat(estado.numero2)
  }
</script>

<template>
    <div class="container bg-secondary p-3">
      <Cabecalho :calcula="calcula()"/>
      <Formulario :trocar-numero1="evento => estado.numero1 = evento.target.value"
        :trocar-numero2="evento => estado.numero2 = evento.target.value" 
        :troca-operacao="evento => estado.operacao = evento.target.value"
        :troca-soma="evento => estado.soma = evento.target.value" 
        :troca-subtracao="evento => estado.subtracao = evento.target.value" 
        :troca-multiplicacao="evento => estado.multiplicacao = evento.target.value" 
        :troca-divisao="evento => estado.divisao = evento.target.value"/>
  </div>
</template>


<style scoped>
.container {
  color: blueviolet;
}
</style>
