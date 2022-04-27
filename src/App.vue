<template>
  <div class="root">
    <div class="component-content">
      <h1>{{ number }} Componente Root</h1>
      <p>
        Esse <b>componente</b> é a raiz do projeto e contempla todos os outros
        componentes no seu template que são importados no script. Nele apenas é
        exportado um <b>data()</b> através do export default.
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
  line-height: 1.5em;
}
h1,
h2 {
  color: black;
}
p {
  text-indent: 1em;
}
.component-content {
  color: #666;
  margin: auto;
  width: 70%;
  padding: 20px;
  margin-bottom: 1em;
  background-color: #f0f0f0;
  box-shadow: 2px 2px 2px rgba(0,0,0,0.3);
}
</style>
