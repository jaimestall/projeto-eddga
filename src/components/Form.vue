<template>
  <h1>Pesquisa por Monstro</h1>
  <form @submit="enviarDados($event)">
    Nome: <input type="text" v-model="name" placeholder="Nome" />
    <button type="submit">Enviar</button>
  </form>
</template>

<script>
export default {
  name: "Formulario",
  data() {
    return {
      name: "",
    };
  },
  methods: {
    enviarDados(e) {
      e.preventDefault();
      if (this.name == "") {
        return alert("Favor informar o nome.");
      } else {
        alert(`Nome enviado: ${this.name}`);
      }
    },
  },
};
</script>
