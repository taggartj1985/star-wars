<template lang="html">
  <div>
   <h4>{{film.title}}</h4>
   <p>Episode: {{film.episode_id}}</p>
   <p>Release Date: {{film.release_date | changeDate}}</p>
   <p>Director: {{film.director}}</p>
 <div>
   <!-- <character-list v-if="characters.length" :characters="characters"></character-list> -->
   <character-list :characters="characters"></character-list>
 </div>
 </div>
</template>

<script>

import CharacterList from './CharacterList.vue';
import moment from 'moment';

export default {
  name: 'film-detail',
  props: ['film'],
  components:{
    'character-list': CharacterList
  },

  data(){
    return{
      characters:[]
    }
  },
  methods: {
  getCharacters(){
    const characterPromises = this.film.characters.map((charactersUrl) => {
      return fetch(charactersUrl).then(res => res.json())
    })
    Promise.all(characterPromises)
    .then(data => this.characters = data);
    }
  },
  mounted(){
    this.getCharacters();
  },
  watch: {
    film: function(){
      this.getCharacters();
    }
  },
  filters:{
    changeDate: function (date) {
    return moment(date).format("DD MMM YYYY");
   },
  }
}
</script>

<style lang="css" scoped>
</style>
