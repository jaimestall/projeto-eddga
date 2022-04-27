<template>
  <div class="component-content">
    <h1>Pesquisa por Monstro</h1>
    <p>
      Neste component tem-se o formulário com
      <b>botão de submit, label e um input-type-text</b>. Neste form usei o
      <b>evento @submit com parâmetro $event</b> chamando a função
      <b>enviarDados(e)</b> do <b>methods</b>.
    </p>
    <p>
      O evento submit com o <b>parâmetro</b> previne que o programa envie
      diretamente os dados do formulário atraves do <b>preventDefault</b> e
      permite que se <b> trabalhe com estes dados antes do envio </b>.
    </p>
    <p>
      Neste component foi utilizada a <b>diretiva v-model</b>. Esta diretiva funciona
      como um aviso para o valor do input de para onde ele deve ir quando for
      submetido. Neste exemplo, o input "Nome" foi enviado para a variável
      'name' do data() deste componente.
    </p>
    <p>Este é o valor digitado no input: {{ name }}</p>
    <form @submit="enviarDados($event)">
      <p>
        <label>
          Nome: <input type="text" v-model="name" placeholder="Nome" />
        </label>
        <button type="submit">Enviar</button>
      </p>
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
