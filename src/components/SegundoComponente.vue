<template>
  <div>
    <h1>{{ number }}Segundo componente</h1>
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
