<template>
  <div class="info-container">
    <div class="data">
      <h3>{{ infos.name }}</h3>
      <div class="infos">
        <p>
          {{ infos.naturality + "," }} {{ infos.civilState + "," }}
          {{ infos.age }} anos
        </p>
        <p>{{ infos.street + "," }} {{ infos.nro }}</p>
        <p>{{ infos.city + "," }} {{ infos.state }}</p>
        <p>Tel/WhatsApp: {{ infos.phone }}</p>
        <p>E-mail: {{ infos.email }}</p>
      </div>
    </div>
    <div class="about">
      <h3>{{ about.title }}</h3>
      <div>
        <p class="about-text">
          {{ about.text }}
        </p>
      </div>
    </div>
    <div class="formation">
      <h3>Formação Acadêmica</h3>
      <div
        class="formations"
        v-for="(formation, index) in formations"
        :key="index"
      >
        <p>
          {{ formation.graduation }} - {{ formation.institution }} -
          {{ formation.years }}.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PersonalInfo",
  data() {
    return {
      infos: {
        name: "Eduardo Lopes Nowakoski",
        naturality: "Brasileiro",
        civilState: "Solteiro",
        age: "29",
        street: "Rua Independência",
        nro: "480",
        city: "Marcelino Ramos",
        state: "RS",
        phone: "(54) 99648-5010",
        email: "eduardo_nowa@hotmail.com",
      },
      formations: [
        {
          graduation: "Engenharia Civil",
          institution: "URI/Erechim",
          years: "2012/2017",
        },
        {
          graduation: "Pós-Graduação em Engenharia de Pavimentação Asfáltica",
          institution: "Faculdade Única",
          years: "2020/2022",
        },
        {
          graduation: "Análise e Desenvolvimento de Sistemas",
          institution: "URI/Erechim",
          years: "2021/Cursando",
        },
      ],
      about: {
        title: "Desenvolvedor Front-End",
        text: "Formado em engenharia civil, fiz uma transição de carreira para a área o qual sou apaixonado, a de tecnologia. Sempre buscando novos conhecimentos e desafios. Tenho experiência com AEM em Vue.js.",
      },
    };
  },
};
</script>

<style lang="scss" scoped>
@import "./PersonalInfo.scss";
</style>
