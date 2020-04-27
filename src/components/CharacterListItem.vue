<template lang="html">
<div class="">
  <h4>{{character.name}}</h4>
  <p>Height:{{character.height}}</p>
  <p>Birthday:{{character.birth_year}}</p>
  </div>
</template>

<script>
export default {
  name: 'character-list-item',
  props: ['character']
}
</script>

<style lang="css" scoped>
</style>
