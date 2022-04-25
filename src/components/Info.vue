<template>
  <div class="component-content">
    <h1>Informações do Monstro</h1>
    <p>
      Aqui no componente de informações eu fiz uso de diretivas v-bind (que pode ser substituida por simples : (dois pontos) antes do atributo desejado). O v-bind atrela determinado atributo à uma variavel do export default { data() { return{} }}.
    </p>
    <p>
      Além disso, fiz uso das diretivas v-show e das condicionais v-if e v-else. A primeira é uma diretiva de exibir ou não uma determinada tag de acordo com o estado dela (true ou false). A segunda tag, v-if e v-else, é uma condicional que requer um argumento do tipo booleano. Se argumento for true, executa o que estiver v-if, caso contrário, executa v-else. Obs: v-else deve sempre estar seguido de v-if.
    </p>
    <p>
      Também, por último foi utilizado um evento @click, que executa determinada função (declarada no export default {methods: {}}) no momento em que o elemento ao qual ela está atrelada for clicado.
    </p>
    <div class="monster">
      <div>
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
  }
  .monster-data {
    display: flex;
    flex-direction: column;
  }
</style>