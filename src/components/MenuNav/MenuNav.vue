<template>
  <nav class="nav-container">
    <div class="menu-tab" v-for="(tab, i) in menuTabs" :key="i">
      <button v-if="i === 0" :class="tab + ' focus'" @click="loadTab(tab)">
        {{ tab }}
      </button>
      <button v-else :class="tab" @click="loadTab(tab)">
        {{ tab }}
      </button>
      <span class="focus-border"></span>
    </div>
  </nav>
</template>

<script>
export default {
  name: "MenuNav",
  data() {
    return {
      menuTabs: ["Informações", "Experiências", "Qualificações"],
    };
  },
  methods: {
    focused(className) {
      this.menuTabs.forEach((tab) => {
        const el = document.querySelector(`.${tab}`);
        el.classList.remove("focus");
      });
      const el = document.querySelector(`.${className}`);
      el.classList.add("focus");
      this.$store.state.actualTab = el.classList[0]
        .toLowerCase()
        .normalize("NFD")
        .replace(/[\u0300-\u036f]/g, "");
    },
    loadTab(tab) {
      this.focused(tab);
    },
  },
};
</script>

<style lang="scss" scooped>
@import "./MenuNav.scss";
</style>
