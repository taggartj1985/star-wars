<template lang="html">
<div class="">
  <h4>{{character.name}}</h4>
  <p>Height:{{character.height | convertToMeters}}</p>
  <p>Birthday:{{character.birth_year | moment("dd, MMMM do YYYY")}}</p>
  </div>
</template>

<script>

export default {
  name: 'character-list-item',
  props: ['character'],
  data(){
    return{}
  },


filters: {
    convertToMeters: function(heightInCm) {
      return heightInCm/100 + 'm';
    },
  }

}
</script>

<style lang="css" scoped>
</style>
