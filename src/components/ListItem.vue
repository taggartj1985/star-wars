<template lang="html">
  <div>
  
      <li>{{film.title}}</li>

  </div>
</template>

<script>
export default {
  name: 'list-item',
  props: ['film'],
}
</script>

<style lang="css" scoped>
</style>
