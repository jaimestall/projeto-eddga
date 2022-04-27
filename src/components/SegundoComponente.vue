<template>
  <div class="component-content">
    <h1>{{ number }}Segundo componente</h1>
    <p>Este é o segundo componente e ele contém um <b>sub componente</b> que nada mais é do que um componente exportado para cá, exatamente da mesma forma que o primeiro componente e este daqui foram exportados para o root. <b>Subcomponentes devem ser chamados no template</b> depois de serem criados e exportados no seu próprio código.</p>
    <sub-componente />
  </div>
</template>

<script>
import subComponente from "./subComponente.vue";

export default {
  name: "SegundoComponente",
  components: {
    subComponente,
  },
  data() {
    return {
      number: "2.1",
    };
  },
};
</script>
