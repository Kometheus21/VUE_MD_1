<template>
  <div id="app">
    <HeaderComponent @login="login" @logout="logout" />
    <div class="content">
      <NavigationComponent :loggedIn="loggedIn" @sectionChange="sectionChange" />
      <div class="mainContent">
        <HomeComponent v-if="loggedIn && currentSection === 'HOME'" />
        <AboutMeComponent v-if="currentSection === 'ABOUT ME'" />
      </div>
    </div>
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import NavigationComponent from "./components/NavigationComponent.vue";
import HomeComponent from "./components/HomeComponent.vue";
import AboutMeComponent from "./components/AboutMeComponent.vue";

export default {
  data() {
    return {
      loggedIn: false,
      currentSection: "HOME",
    };
  },
  components: {
    HeaderComponent,
    NavigationComponent,
    HomeComponent,
    AboutMeComponent,
  },
  methods: {
    login() {
      this.loggedIn = true;
      this.currentSection = "HOME";
    },
    logout() {
      this.loggedIn = false;
      this.currentSection = "HOME";
    },
    sectionChange(section) {
      this.currentSection = section;
    },
  },
};
</script>

<style>
</style>