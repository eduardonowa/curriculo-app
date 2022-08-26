<template>
  <div class="quali-container">
    <h3>Qualificações</h3>
    <div class="list" v-for="(item, index) in itens" :key="index">
      <li>{{ item }}</li>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line
  name: "Qualifications",
  data() {
    return {
      itens: [
        "Conhecimento em tecnologias de desenvolvimento web (HTML, CSS, SASS, JavaScript)",
        "Desenvolvimento de aplicações web com o frameworks Vue.js.",
        "Conhecimento em ferramentas de testes e versionamento de código (Jest, Git)",
        "Metodologias Ágeis (Scrum, Kanban)",
        "Conhecimento em Sistema de Gestão de Conteúdos(AEM)",
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "./Qualifications.scss";
</style>
