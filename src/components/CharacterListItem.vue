<template lang="html">
  <h4>{{character.name}}</h4>
  <!-- <p>{{character.height}}</p> -->
</template>

<script>
export default {
  name: 'character-list-item',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
