<template>
  <PrimeiroComponente />
  <p>O componente que abriga componentes também pode conter dados. {{ info }}</p>
</template>

<script>
import PrimeiroComponente from './components/PrimeiroComponente.vue'

export default {
  name: 'App',
  components: {
    PrimeiroComponente,
  },
  data () {
    return {
      info: '>>Exemplo de dado trazido do data() do componente principal<<',
    }
  }
}
</script>