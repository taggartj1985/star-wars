<template lang="html">
<div class="">
  <h4>{{character.name}}</h4>
  <p>Height:{{character.height | convertToMeters}}</p>
  <p>Birthday:{{character.birth_year}}</p>
  <p>Homeworld:{{homeworld.name}}</p>
  <p>Terrain:{{homeworld.terrain}}</p>
  </div>
</template>

<script>
var moment = require('moment');


export default {
  name: 'character-list-item',
  props: ['character'],
  data(){
    return{
      homeworld:[]
    }
  },

  mounted() {
    this.getHomeWorld();
  },
  methods: {
    getHomeWorld: function() {
      fetch(this.character.homeworld)
      .then(response => response.json())
      .then(data => this.homeworld = data);
    },
  },


filters: {
    convertToMeters: function(heightInCm) {
      return heightInCm/100 + 'm';
    },
    changeDate: function (date) {
    return moment(date).format("dd, MMM do YYYY");
  },
  }

}
</script>

<style lang="css" scoped>
</style>
