<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';
  import Resultado from './components/Resultado.vue';

  const estado = reactive({
    operacao: 'somar',
    campo1: 0,
    campo2: 0,
    resultado: 0,
  });

  const atualizaCampo1 = (evento) => {
    estado.campo1 = Number(evento.target.value);

    const { operacao } = estado;

    switch (operacao) {
      case 'somar':
        return estado.resultado = estado.campo1 + estado.campo2;
      case 'subtrair':
        return estado.resultado = estado.campo1 - estado.campo2;
      default:
        return estado.resultado = estado.campo1 * estado.campo2;
    }
  };

  const atualizaCampo2 = (evento) => {
    estado.campo2 = Number(evento.target.value);

    const { operacao } = estado;

    switch (operacao) {
      case 'somar':
        return estado.resultado = estado.campo1 + estado.campo2;
      case 'subtrair':
        return estado.resultado = estado.campo1 - estado.campo2;
      default:
        return estado.resultado = estado.campo1 * estado.campo2;
    }
  };

  const trocarOperacao = (evento) => {
    estado.operacao = evento.target.value;
    const { operacao } = estado;

    switch (operacao) {
      case 'somar':
        return estado.resultado = estado.campo1 + estado.campo2;
      case 'subtrair':
        return estado.resultado = estado.campo1 - estado.campo2;
      default:
        return estado.resultado = estado.campo1 * estado.campo2;
    }
  };
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario 
      :atualiza-campo1="atualizaCampo1" 
      :atualiza-campo2="atualizaCampo2" 
      :valor-campo1="estado.campo1"
      :valor-campo2="estado.campo2"
      :trocar-operacao="trocarOperacao"
      :operacao="estado.operacao"
    />
    <Resultado :resultado="estado.resultado" />
  </div>
</template>
