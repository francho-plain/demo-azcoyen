<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>


<template>
  <v-app>
    <v-app-bar color="primary" dark>
      <v-app-bar-title>Demo Azcoyen Copilot Tasks</v-app-bar-title>
    </v-app-bar>
    <v-main>
      <v-container class="mt-5">
        <HelloWorld msg="¡Vuetify está funcionando!" />
        <TheWelcome />
      </v-container>
    </v-main>
  </v-app>
</template>

<style scoped>
/* Puedes personalizar estilos aquí si lo deseas */
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
