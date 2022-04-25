<template>
  <div class="component-content">
    <h1>Pesquisa por Monstro</h1>
    <p>
      Neste component tem-se o formulário com label, input e o botão de submit.
      Neste form usei o evento @submit com parâmetro $event chamando a função
      enviarDados(e) do methods.
    </p>
    <p>
      O evento submit com o parâmetro previne que o programa envie diretamente
      os dados do formulário atraves do preventDefault e permite que se trabalhe
      com estes dados antes do envio.
    </p>
    <p>
      Além disso, no input foi informado o v-model="name" que representa que, ao
      ser enviado o formulário com alguma informação naquele input, os dados vão
      direto para a variável "name = ''" do campo data() { return {}} na sessão
      de export do proprio component.
    </p>
    <form @submit="enviarDados($event)">
      <label>Nome: </label>
      <input type="text" v-model="name" placeholder="Nome" />
      <button type="submit">Enviar</button>
    </form>
  </div>
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
