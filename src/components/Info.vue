<template>
  <div class="component-content">
    <h1>Informações do Monstro</h1>
    <p>
      Aqui no componente de informações eu fiz uso de diretivas<b> v-bind</b>
      (que pode ser substituida por simples : (dois pontos) antes do atributo
      desejado). O v-bind atrela determinado <b>atributo de uma tag</b> (href,
      src, target ) à uma <b>variavel</b> do data().
    </p>
    <p>
      Além disso, fiz uso das diretivas <b>v-show, v-if e v-else</b>. A primeira
      é uma diretiva de exibir ou não uma determinada tag de acordo com o estado
      dela (true ou false). A segunda tag, v-if e v-else, é uma condicional que
      requer um argumento do tipo <b>booleano</b>. Se argumento for true,
      executa o que estiver v-if, caso contrário, executa v-else. Obs:
      <b>v-else deve sempre estar seguido de v-if</b>.
    </p>
    <p>
      Também, por último foi utilizado um <b>evento @click</b>, que executa
      determinada função declarada methods no momento em que o elemento ao qual
      ela está atrelada for clicado.
    </p>
    <h2>Exemplo</h2>
    <div class="monster">
      <div class="monster-photo">
        <img :src="profilePic" :alt="description" />
      </div>
      <div class="monster-data">
        <p>Servidor: {{ server }}</p>
        <p><button @click="changeServerType">Mudar o servidor</button></p>
        <p>Nome: {{ name }}</p>
        <p>Elemento: {{ element }}</p>
        <p>Raça: {{ race }}</p>
        <p v-if="server == 'renewal'">Localização: pay_fild10</p>
        <p v-else>Localização: pay_fild11</p>
        <p v-show="respawn">Tempo de Respawn: 2h</p>
        <p><a v-bind:href="rateMyServer" target="_blank">Rate my server</a></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Info",
  data() {
    return {
      profilePic: "/img/eddga.png",
      description: "Eddga",
      name: "Eddga",
      element: "Fogo",
      race: "Bruto",
      server: "renewal",
      respawn: true,
      rateMyServer:
        "https://ratemyserver.net/index.php?page=mob_db&mob_id=1115",
    };
  },
  methods: {
    changeServerType() {
      if (this.server == "renewal") {
        this.server = "pre-renewal";
      } else {
        this.server = "renewal";
      }
    },
  },
};
</script>
<style scoped>
.monster {
  display: flex;
  align-content: center;
}
.monster-data {
  display: flex;
  flex-direction: column;
  align-items: left;
}
@media screen and (max-width: 700px) {
  .monster {
    flex-direction: column;
    align-items: center;
  }
}
</style>
