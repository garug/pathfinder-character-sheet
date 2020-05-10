<template>
  <v-select
    :items="items"
    v-model="selected"
    item-text="name"
    label="Herança"
    :disabled="!items || items.length === 0"
  />
</template>

<script lang="ts">
import { Component, Vue, Watch, Prop } from 'vue-property-decorator';
import { Heritage } from './Ancestry.vue';

@Component
export class HeritageSelect extends Vue {
  selected: string | null = null;

  @Prop() items: Array<Heritage> | undefined;

  @Watch('items')
  onItemsChange() {
    this.selected = null;
  }
}
export default HeritageSelect;
</script>
