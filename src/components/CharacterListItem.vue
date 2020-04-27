<template lang="html">
<div class="">
  <h4>{{character.name}}</h4>
  <p>Height:{{character.height | convertToMeters}}</p>
  <p>Birthday:{{character.birth_year | changeDate}}</p>
  </div>
</template>

<script>
var moment = require('moment');


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
    changeDate: function (date) {
    return moment(date).format("dd, MM do YYYY");
  },
  }

}
</script>

<style lang="css" scoped>
</style>
