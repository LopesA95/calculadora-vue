<script>
export default {
  name: 'Operacoes',
  props: {
    operacao: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      operacaoLocal: this.operacao,
    };
  },
  watch: {
    operacaoLocal() {
      this.$emit('trocar-operacao', this.operacaoLocal);
    },
    operacao(newOperacao) {
      this.operacaoLocal = newOperacao;
    },
  },
};
</script>

<template>
  <select class="form-control" v-model="operacaoLocal">
    <option value="soma">Soma</option>
    <option value="subtracao">Subtração</option>
    <option value="multiplicacao">Multiplicação</option>
    <option value="divisao">Divisão</option>
  </select>
</template>
