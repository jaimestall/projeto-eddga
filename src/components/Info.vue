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
      Também foi utilizado um <b>evento @click</b>, que executa determinada
      função declarada methods no momento em que o elemento ao qual ela está
      atrelada for clicado.
    </p>
    <p>
      Por último foi utilizado o <b>v-for para renderização de lista</b>. A
      diretiva v-for funciona em partes como o for do Javascript, entretanto a
      formação do v-for é um pouco diferente. Primeiro
      <b>apenas um elemento</b> de um array (de itens ou mesmo de objetos) que
      vem do data(): <b>v-for="drop in droppedItem"</b>. Então este item será
      "iterado" e formará a lista. Em seguida é colocado o
      <b>atributo key junto de um v-bind</b> (lembrando que pode-se colocar a
      abreviação :key="" para v-bind) e nele passa-se o indice do elemento
      iterado.
    </p>
    <p>
      Obs: Se o array iterado for um array de elementos e não tiver indicado
      qual o índice de cada elemento (que seria o caso para um possivel array de
      objetos), então, junto do elemento desejado de dentro do array, passa-se o
      atributo oculto do Javascript:
    </p>
    <p>
      Exemplo de tag contendo v-for quando array não contém índice:
      <b>[["tag v-for="(item, index) in itens" :key="index"]]</b>
    </p>
    <h2>Exemplo</h2>
    <div class="monster">
      <div class="monster-photo">
        <img class="photo" :src="profilePic" :alt="description" />
      </div>
      <div class="monster-info">
        <div class="info-basica">
          <h3>
            <p>Informações</p>
          </h3>
          <p>Servidor: {{ server }}</p>
          <p><button @click="changeServerType">Mudar o servidor</button></p>
          <p>Nome: {{ name }}</p>
          <p>Elemento: {{ element }}</p>
          <p>Raça: {{ race }}</p>
          <p v-if="server == 'renewal'">Localização: pay_fild10</p>
          <p v-else>Localização: pay_fild11</p>
          <p v-show="respawn">Tempo de Respawn: 2h</p>
          <p>
            <a v-bind:href="rateMyServer" target="_blank">Rate my server</a>
          </p>
        </div>
        <div class="info-drops">
          <h3>Itens Derrubados</h3>
          <ul>
            <li v-for="drop in droppedItem" :key="drop.id">
              {{ drop.itemName }}
            </li>
          </ul>
        </div>
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
      droppedItem: [
        { id: 1, itemName: "Elunium" },
        { id: 2, itemName: "Mel" },
        { id: 3, itemName: "Pele de Tigre" },
        { id: 4, itemName: "Carta Eddga" },
        { id: 5, itemName: "Cachimbo" },
      ],
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
.info-basica {
  display: flex;
  flex-direction: column;
}
.info-drops {
  display: flex;
  flex-direction: column;
  margin-left: 1em;
}
.monster {
  display: flex;
  align-content: center;
}
.monster-info {
  display: flex;
  align-items: left;
  justify-content: space-between;
}
@media screen and (max-width: 1100px) {
  .monster {
    flex-direction: column;
    align-items: center;
  }
}
</style>
