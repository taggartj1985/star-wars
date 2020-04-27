<template lang="html">
  <div>
    <h3>Character List</h3>

      <character-list-item v-for="(character, index) in characters" :character="character" :key="index" ></character-list-item >

  </div>
</template>

<script>

import CharacterListItem from './CharacterListItem.vue';

export default {
  name: 'character-list',
  props: ['characters'],
  components: {
    'character-list-item': CharacterListItem
  }
}
</script>

<style>
</style>
