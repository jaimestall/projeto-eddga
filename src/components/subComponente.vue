<template>
  <div>
    <h2>{{ number }} subComponente </h2>
    <p>Em subcomponentes nota-se que ele herda a classe e a estilização do componente pai. Isso quer dizer que este template não necessita estilização própria, <span class="span-exemplo">mas se quiser pode ser feita uma estilização à parte como este trecho</span></p>
  </div>
</template>

<script>
export default {
  name: 'subComponente',
  data() {
    return {
      number: '2.2',
    }
  }
}
</script>
<style>
  .span-exemplo {
    color: red;
  }
</style>