<template>
  <div class="exp-container">
    <div v-for="(experience, index) in experiences" :key="index">
      <h3>
        {{ experience.job }} - {{ experience.duration }}
        <img
          :src="require('@/assets/' + experience.imgSrc)"
          alt="arrow"
          class="arrowImg"
          @click="check(index)"
        />
      </h3>
      <div class="description" v-if="showDescription.includes(experience.id)">
        <p  class="company-name">{{ experience.company }}.</p>
        <p>Cargo: {{ experience.job }}.</p>
        <p>Principais atividades: {{ experience.description }}.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line
  name: "Experiences",
  data() {
    return {
      experiences: [
        {
          id: "intern",
          job: "Estagiário",
          duration: "Mai-2022/Ago-2022",
          company: "Compass.UOL",
          description:
            "Bolsa de estudos voltada para a execução de projetos com a plataforma AEM utilizando Vue.js",
          imgSrc: "arrow-down.png"
        },
        {
          id: "civil_eng",
          job: "Engenheiro Civil",
          duration: "Fev-2017/Mai-2022",
          company: "NG Engenharia",
          description:
            "Projetos arquitetônicos, estruturais, elétricos e hidrossanitários; Parcelamentos de solo; Regularizações; Acompanhamento de execução em todas etapas da obra; Avaliação de imóveis",
          imgSrc: "arrow-down.png"
        },
        {
          id: "intern_1",
          job: "Estagiário",
          duration: "Ago-2015/Fev-2017",
          company: "Prefeitura Municipal de Marcelino Ramos",
          description:
            "Análise de projetos e documentações para aprovação; Expedição de certidões; Elaboração de projetos; Acompanhamento de obras públicas, tanto na área de construção civil quanto pavimentação",
          imgSrc: "arrow-down.png"
        },
        {
          id: "intern_2",
          job: "Estagiário",
          duration: "Set-2014/Dez-2014",
          company: "Traçado Construções e Serviços LTDA",
          description:
            "Controle de produção, material e mão de obra de obras rodoviárias; Busca de soluções para otimização da produção das obras",
          imgSrc: "arrow-down.png"
        },
      ],
      showDescription: [],
    };
  },
  methods: {
    check(index) {
      const $ = this.experiences[index].id;
      this.experiences[index].imgSrc
      const addItemToShow = (experience) => {
        this.showDescription = [...this.showDescription, experience];
      };
      const hideItem = (experience) => {
        this.showDescription = this.showDescription.filter(
          (id) => id !== experience
        );
      };
      if (this.showDescription.includes($)) {
        this.experiences[index].imgSrc = "arrow-down.png"
        hideItem($);
      } else {
        this.experiences[index].imgSrc = "arrow-above.png"
        addItemToShow($);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "./Experiences.scss";
</style>
