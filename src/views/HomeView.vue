<template>
  <div class="home">
    <Title />
    <MenuNav />
    <Tabs />
    <Footer />
  </div>
</template>

<script>
import MenuNav from "@/components/MenuNav/MenuNav.vue";
import Tabs from "@/components/Tabs/Tabs.vue";
import Footer from "@/components/Footer/Footer.vue";
import Title from "@/components/Title/Title.vue";
export default {
  name: "HomeView",
  components: {
    MenuNav,
    Tabs,
    Footer,
    Title
  },
};
</script>

<style lang="scss" scoped>
.home {
  width: 70%;
  margin: 0 auto;
  @media(max-width:630px){
    width: 100%;
  }
}

</style>
