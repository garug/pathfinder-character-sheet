<template>
  <v-app>
    <!-- <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar> -->

    <v-content>
      <CharacterSheet />
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from './components/HelloWorld.vue';
import CharacterSheet from './components/CharacterSheet.vue';
import { Component } from 'vue-property-decorator';

@Component({
  components: {
    HelloWorld,
    CharacterSheet,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  background: url('./assets/bg.jpg');
}

h1,
h2,
h3,
h4,
h5,
h6 {
  color: #5e0000;
  font-family: 'Asap Condensed', sans-serif;
  font-weight: 600;
}
</style>
