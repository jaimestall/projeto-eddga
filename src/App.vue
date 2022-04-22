<template>
  <h1>{{ number }} Componente Root</h1>
  <primeiro-componente />
  <segundo-componente />
  <formulario />
  <info />
</template>

<script>
import PrimeiroComponente from "./components/PrimeiroComponente.vue";
import SegundoComponente from "./components/SegundoComponente.vue";
import Formulario from "./components/Form.vue";
import Info from "./components/Info.vue";

export default {
  name: "App",
  components: {
    PrimeiroComponente,
    SegundoComponente,
    Formulario,
    Info,
  },
  data() {
    return {
      number: "1",
    };
  },
};
</script>
