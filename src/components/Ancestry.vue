<template>
  <div>
    <v-select
      :items="items"
      item-text="name"
      label="Ancestralidade"
      @change="emitAncestry"
      v-model="selected"
    >
    </v-select>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Emit } from 'vue-property-decorator';

export interface AncestryEntity {
  name: string;
  attributes?: Array<Attribute>;
  heritages?: Array<Heritage>;
  feats?: Array<Feat>;
}

export interface Attribute {
  name: string;
  short: string;
}

export interface Heritage {
  name: string;
}

export interface Feat {
  name: string;
  level: number;
}

@Component
export class Ancestry extends Vue {
  @Emit('change')
  emitAncestry() {
    return this.items.find(e => e.name === this.selected);
  }

  selected: string | null = null;

  items: Array<AncestryEntity> = [
    {
      name: 'Anão',
      heritages: [
        {
          name: 'Anão da Forja',
        },
        {
          name: 'Anão Guardião da Morte',
        },
        {
          name: 'Anão das Rochas',
        },
        {
          name: 'Anão de Sangue Ancestral',
        },
        {
          name: 'Anão de Sangue Forte',
        },
      ],
    },
    {
      name: 'Elfo',
    },
    {
      name: 'Gnomo',
    },
    {
      name: 'Goblin',
      attributes: [
        { name: 'Destreza', short: 'des' },
        { name: 'Carisma', short: 'car' },
        { name: 'Livre', short: 'free' },
      ],
      heritages: [
        {
          name: 'Goblin Bucho-de-Ferro',
        },
        {
          name: 'Goblin Couro-Chamuscado',
        },
        {
          name: 'Goblin Dentes-de-Navalha',
        },
        {
          name: 'Goblin Inquebrável',
        },
        {
          name: 'Goblin das Neves',
        },
      ],
      feats: [
        {
          name: 'Canção de Goblin',
          level: 1,
        },
        {
          name: 'Catador da Cidade',
          level: 1,
        },
        {
          name: 'Cavaleiro Brusco',
          level: 1,
        },
        {
          name: 'Familiaridade com Armas Goblinoides',
          level: 1,
        },
        {
          name: 'Funileiro de Sucata',
          level: 1,
        },
        {
          name: 'Muito Sorrateiro',
          level: 1,
        },
        {
          name: 'Passadela Goblin',
          level: 1,
        },
        {
          name: 'Saber Goblin',
          level: 1,
        },
        {
          name: 'Taca Fogo!',
          level: 1,
        },
      ],
    },
    {
      name: 'Humano',
    },
    {
      name: 'Halfling',
    },
  ];
}

export default Ancestry;
</script>

<style></style>
