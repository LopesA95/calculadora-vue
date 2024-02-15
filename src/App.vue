<!-- App.vue -->
<template>
  <div id="app" class="container">

    <Calculadora />

  </div>
</template>

<script>
import Calculadora from './components/Calculadora.vue';

export default {
  name: 'App',
  components: {
    Calculadora,
  },
};
</script>


