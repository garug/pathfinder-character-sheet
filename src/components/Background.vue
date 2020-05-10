<template>
  <v-select :items="items" item-text="name" label="Biografia" />
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';

@Component
export default class Background extends Vue {
  items = [
    {
      name: 'Anão',
    },
    {
      name: 'Elfo',
    },
    {
      name: 'Gnomo',
    },
    {
      name: 'Goblin',
    },
    {
      name: 'Humano',
    },
    {
      name: 'Halfling',
    },
  ];
}
</script>

<style></style>
