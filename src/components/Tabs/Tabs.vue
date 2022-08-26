<template>
  <div class="tabs-container">
    <PersonalInfo v-if="this.$store.state.actualTab === 'informacoes'" />
    <Experiences v-if="this.$store.state.actualTab === 'experiencias'"/>
    <Qualifications  v-if="this.$store.state.actualTab === 'qualificacoes'"/>
  </div>
</template>

<script>
import PersonalInfo from "@/components/Tabs/PersonalInfo/PersonalInfo.vue";
import Experiences from '@/components/Tabs/Experiences/Experiences.vue'
import Qualifications from '@/components/Tabs/Qualifications/Qualifications.vue'

export default {
  // eslint-disable-next-line
  name: "Tabs",
  components: { PersonalInfo , Experiences, Qualifications },
};
</script>

<style lang="scss">
@import "./Tabs.scss";
</style>
