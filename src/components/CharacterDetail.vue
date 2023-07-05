<template>
  <div v-if="character">
    <h2>{{ character.name }}</h2>
    <img :src="character.thumbnail.path + '/portrait_xlarge.' + character.thumbnail.extension" :alt="character.name">
    <p>{{ character.description }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      character: null
    };
  },
  props: ['characterId'],
  watch: {
    characterId: {
      immediate: true,
      handler(newId) {
        if (newId) {
          this.fetchCharacter(newId);
        }
      }
    }
  },
  methods: {
    fetchCharacter(id) {
      axios
        .get(`https://gateway.marvel.com/v1/public/characters/${id}`, {
          params: {
            apikey: '8c4925921c89ac09e7a917f18cba5de4'
          }
        })
        .then(response => {
          this.character = response.data.data.results[0];
        })
        .catch(error => {
          console.error(error);
        });
    }
  }
};
</script>