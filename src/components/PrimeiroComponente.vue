<template>
  <div class="component-content">
    <h1>{{ number }}Primeiro componente</h1>
    <p>Este componente tem apenas o intuito de ser o primeiro componente exportado pelo <b>Root</b>. Também foi passado um dado pelo <b>export default</b> para o título.</p>
  </div>
</template>

<script>
export default {
  name: "PrimeiroComponente",
  data() {
    return {
      number: "1.1",
    };
  },
};
</script>
