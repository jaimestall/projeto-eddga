<template>
  <h1>Informações do Monstro</h1>
  <div>
    <p>
      <img :src="profilePic" :alt="description" />
    </p>
    <p>Nome: {{ name }}</p>
    <p>Elemento: {{ element }}</p>
    <p>Raça: {{ race }}</p>
    <p v-if="server == 'renewal'">Localização: pay_fild10</p>
    <p v-else>Localização: pay_fild11</p>
    <p v-show="respawn">Tempo de Respawn: 2h</p>
    <p><a :href="rateMyServer" target="_blank">Rate my server</a></p>
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
};
</script>
