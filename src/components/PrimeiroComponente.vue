<template>
  <div class="component">
    <h1>Component principal</h1>
    <p>Nome: {{ name }}</p>
    <p>Elemento: {{ elemento }}</p>
  </div>
</template>

<script>
export default {
  name: "PrimeiroComponente",
  data() {
    return {
      name: "Eddga",
      elemento: "Fogo",
    };
  },
};
</script>
<style scoped>
.component {
  border: 1px solid black;
  padding-left: 1em;
}
</style>
