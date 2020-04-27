<template lang="html">
  <li>{{character.name}}</li>
</template>

<script>
export default {
  name: 'character-list-item',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
