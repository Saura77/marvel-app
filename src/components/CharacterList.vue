<template>
    <div>
      <h2>Character List</h2>
      <ul>
        <li v-for="character in characters" :key="character.id">
            {{ character.name }}
            <button @click="showCharacterDetail(character.id)">View Details</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        characters: []
      };
    },
    methods:{
        showCharacterDetail(characterId) {
            this.$emit('character-selected', characterId);
        }
    },
    mounted() {
      axios
        .get('https://gateway.marvel.com/v1/public/characters', {
          params: {
            apikey: '8c4925921c89ac09e7a917f18cba5de4',
            orderBy: "modified",
            limit: 25
          }
        })
        .then(response => {
          this.characters = response.data.data.results;
          console.log(this.characters);
        })
        .catch(error => {
          console.error(error);
        });
    }
  };
  </script>