<template>
  <v-select
    :items="items"
    :disabled="!items || items.length === 0"
    v-model="selected"
    item-text="name"
    label="Talento"
  />
</template>

<script lang="ts">
import { Component, Vue, Prop, Watch } from 'vue-property-decorator';
import { Feat } from './Ancestry.vue';

@Component
export class FeatSelect extends Vue {
  selected = null;

  @Prop() items: Array<Feat> | undefined;

  @Watch('items')
  onItemsChange() {
    this.selected = null;
  }
}

export default FeatSelect;
</script>
