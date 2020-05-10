<template>
  <v-container>
    <h1>Pathcreator</h1>
    <v-row>
      <v-col cols="12">
        <h2 class="w-100">Informações Iniciais</h2>
      </v-col>
      <v-col>
        <Ancestry @change="handleAncestry" />
      </v-col>
      <v-col>
        <Background />
      </v-col>
      <v-col>
        <CharacterClass />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <h2 class="w-100">nv 1</h2>
      </v-col>
      <v-col>
        <HeritageSelect :items="(ancestry || {}).heritages" />
      </v-col>
      <v-col>
        <FeatSelect :items="avaliableFeats" />
      </v-col>
      <v-col>
        <AbilityBoosts />
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator';
import Ancestry, { AncestryEntity, Heritage } from './Ancestry.vue';
import Background from './Background.vue';
import CharacterClass from './CharacterClass.vue';
import HeritageSelect from './HeritageSelect.vue';
import FeatSelect from './FeatSelect.vue';
import AbilityBoosts from './AbilityBoosts.vue';

@Component({
  components: {
    Ancestry,
    Background,
    CharacterClass,
    HeritageSelect,
    FeatSelect,
    AbilityBoosts,
  },
})
export default class CharacterSheet extends Vue {
  ancestry: AncestryEntity | null = null;

  heritage: Heritage | null = null;

  @Watch('ancestry')
  onAncestryChange() {
    this.heritage = null;
  }

  handleAncestry(newAncestry: AncestryEntity) {
    this.ancestry = newAncestry;
  }

  get avaliableFeats() {
    return this.ancestry?.feats;
  }
}
</script>

<style>
.container {
  background: rgba(227, 222, 214, 0.8);
  padding: 5vh 50px;
}
</style>
