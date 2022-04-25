<template>
  <div class="content">
    <div class="component-content">
      <h1>{{ number }} Componente Root</h1>
      <p>
        esse componente é a raiz do projeto e contempla todos os outros
        componentes. Nele apenas é exportado um valor pelo export default {
        data() {}} e exportados os components atraves do export default {
        components: {}}. Também são importados todos os outros componentes no
        script e chamados no template do Root.
      </p>
    </div>
    <primeiro-componente />
    <segundo-componente />
    <formulario />
    <info />
  </div>
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
<style>
* {
  padding: 0;
  margin: 0;
  font-family: "Open Sans", sans-serif;
}
.component-content {
  color: black;
  margin: auto;
  width: 60%;
  text-indent: 1em;
}
</style>
