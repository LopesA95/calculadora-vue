<template>
  <header class="p-5 mb-4 mt-4 bg-light rounded-3 text-center">
    <h1 class="mb-4">Calculadora Aritmética</h1>
    <div class="row justify-content-center">
      <div class="col-md-4">
        <input type="number" class="form-control" v-model="num1" placeholder="Primeiro Número">
      </div>
      <div class="col-md-4">
        <input type="number" class="form-control" v-model="num2" placeholder="Segundo Número">
      </div>
    </div>
    <div class="row mt-3 justify-content-center">
      <div class="col-md-3">
        <Operacoes :operacao="operacao" @trocar-operacao="trocarOperacao" />
      </div>
    </div>
    <div class="row mt-3 justify-content-center">
      <div class="col-md-3">
        <h2>{{ resultado }}</h2>
      </div>
    </div>
  </header>
</template>

<script>
import Operacoes from './Operacoes.vue';

export default {
  components: {
    Operacoes,
  },
  data() {
    return {
      num1: '',
      num2: '',
      operacao: '',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case 'soma':
          return parseFloat(this.num1) + parseFloat(this.num2);
        case 'subtracao':
          return parseFloat(this.num1) - parseFloat(this.num2);
        case 'multiplicacao':
          return parseFloat(this.num1) * parseFloat(this.num2);
        case 'divisao':
          return parseFloat(this.num1) / parseFloat(this.num2);
        default:
          return 0;
      }
    },
  },
  methods: {
    trocarOperacao(novaOperacao) {
      this.operacao = novaOperacao;
    },
  },
};
</script>
