<template lang="html">
  <div>
    <h3>Character List</h3>
    <ul>
      <character-list-item v-for="(character, index) in characters" :key="index" :character="character"></character-list-item >
    </ul>
  </div>
</template>

<script>

import CharacterListItem from './CharacterListItem.vue'

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
