<template>
  <div>
    <h1>{{ number }}Primeiro componente</h1>
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
