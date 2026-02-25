<script setup>
import { ref, computed } from 'vue'
import home from './home.vue'
import about from './about.vue'

const routes = {
  '/': home,
  '/about': about
}

const currentPath = ref(window.location.hash)
const drawer = ref(false)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
  <v-app>
    <v-navigation-drawer class="text-white"
                         v-model="drawer"
                         color="green-darken-3"
    >
      <v-list-item
          prepend-icon="mdi-home"
          href="#/"
          title="Home"
          @click="drawer = !drawer"
      ></v-list-item>
      <v-list-item
          prepend-icon="mdi-information-variant-circle-outline"
          href="#/about"
          title="About Us"
          @click="drawer = !drawer"
      ></v-list-item>
    </v-navigation-drawer>
    <v-app-bar
        class="text-white"
        height="200"
        color="green-darken-4">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-app-bar-title class="text-h1 text-center cedarville-cursive-regular">Jon & Kristen</v-app-bar-title>
    </v-app-bar>
    <v-main>
      <component :is="currentView"></component>
    </v-main>
    <v-footer app="false">Copyright 2026</v-footer>
  </v-app>
</template>

<style scoped>
.cedarville-cursive-regular {
  font-family: "Cedarville Cursive", cursive;
  font-weight: 400;
  font-style: normal;
  line-height: 4;
}

</style>