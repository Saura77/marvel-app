<template>
  <div>
    <CharacterList @character-selected="showCharacterDetail" />
    <CharacterDetail v-if="selectedCharacterId" :characterId="selectedCharacterId" />  
  </div>
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import CharacterDetail from './components/CharacterDetail.vue';

export default {
  components: {
    CharacterList,
    CharacterDetail
  },
  data() {
    return {
      selectedCharacterId: null
    };
  },
  methods: {
    showCharacterDetail(characterId) {
      this.selectedCharacterId = characterId;
      console.log(characterId);
    }
  }
};
</script>