<template>
  <h1>{{ number }} Componente Root</h1>
  <PrimeiroComponente />
  <SegundoComponente />
</template>

<script>
import PrimeiroComponente from "./components/PrimeiroComponente.vue";
import SegundoComponente from "./components/SegundoComponente.vue";

export default {
  name: "App",
  components: {
    PrimeiroComponente,
    SegundoComponente,
  },
  data() {
    return {
      number: "1",
    };
  },
};
</script>
