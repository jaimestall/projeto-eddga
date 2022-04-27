<template>
  <div>
    <h2>{{ number }} subComponente</h2>
    <p>
      Em subcomponentes, nota-se que ele
      <b>herda a classe e a estilização do componente pai</b>. Isso quer dizer
      que este template não necessita estilização própria,
      <span class="span-exemplo"
        >mas se quiser pode ser feita uma estilização à parte como este
        trecho</span
      >
    </p>
    <p>
      <b>Props</b> passada pelo componente pai para o componente filho:
      {{ emailProps }}
    </p>
  </div>
</template>

<script>
export default {
  name: "subComponente",
  props: {
    emailProps: String,
  },
  data() {
    return {
      number: "2.2",
    };
  },
};
</script>
<style>
.span-exemplo {
  color: white;
  background-color: #666;
}
</style>
