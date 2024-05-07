<script>
export default {
    data() {
        return {
            scrollPosition: 0,
            drawer: false,
        };
    },
    methods: {
        onScroll() {
            this.scrollPosition = window.scrollY;
        },
    },
    computed: {
        appBarColor() {
            return this.scrollPosition > 5 ? 'rgba(49, 27, 146)' : 'transparent';
        },
    },
};
</script>

<template>
    <v-app v-scroll="onScroll">
      <v-app-bar :color="appBarColor" scroll-behavior="elevate" scroll-threshold="40">
        <v-row align="center">
            <router-link to="/"  style="text-decoration: none;">        
                <div style="display: flex; align-items: center;">
                    <v-avatar class="mr-2 ml-10" color="primary">&lt;/&gt;</v-avatar>
                    <v-toolbar-title class="text-white" style="font-weight: 800;">JuanFourThree</v-toolbar-title>
                </div>
            </router-link>
            <v-spacer></v-spacer>
            <v-app-bar-nav-icon @click="drawer = !drawer" class="hidden-md-and-up" icon="mdi-menu"></v-app-bar-nav-icon>
            <v-tabs class="text-white mr-10">
                <v-tab to="/" class="hidden-sm-and-down">Home</v-tab>
                <v-tab to="/projects" class="hidden-sm-and-down">Projects</v-tab>
                <v-tab to="/contacts" class="hidden-sm-and-down">Contacts</v-tab>
            </v-tabs>
        </v-row>
      </v-app-bar>

      <v-navigation-drawer v-model="drawer" app temporary class="hidden-md-and-up">
        <v-list>
          <v-list-item link to="/"><p class="text-black">Home</p></v-list-item>
          <v-list-item link to="/projects"><p class="text-black">Projects</p></v-list-item>
          <v-list-item link to="/contacts"><p class="text-black">Contacts</p></v-list-item>
        </v-list>
      </v-navigation-drawer>
      <router-view style="overflow-y: hidden; overflow-x: hidden;"></router-view>
    </v-app>
  </template>
 
<style>
* {
    font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: #F5F5F5;
}
@media (min-width: 960px) {
  .hidden-md-and-up {
    display: none;
  }
  .demo-device {
    display: flex;
  }
}
@media (max-width: 959px) {
  .hidden-sm-and-down {
    display: none;
  }
}
</style>