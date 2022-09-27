<template>
  <div id="app">
    <headerComponent/>
    <loaderComponent v-if="loading" />
    <mainComponent :songs="songsToShow" @changedGenre="choiceOption" />
  </div>
</template>

<script>

import axios from 'axios';

import headerComponent from './components/headerComponent.vue'
import mainComponent from './components/mainComponent.vue'
import loaderComponent from './components/loaderComponent.vue'


export default {
  name: 'App',
  components: {
    headerComponent,
    mainComponent,
    loaderComponent,
    
},
  data() {
    return{
      apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      songs: [],
      errorMessage:'',
      loading:true,
      option:'',

    };
  },

  created() {
    axios
      .get(this.apiUrl)
      .then(({ status, data }) => {
        this.loading = false;
        if (status === 200) {
          this.songs = data.response;
          console.log(this.songs)
        } else {
          this.errorMessage = 'something went wrong...';
        }
      })
      .catch((error) => {
        console.log(error);
        this.loading = false;
        this.errorMessage = 'error: ' + error.message;
      });
  },

  methods:{
    choiceOption(option){
      this.option=option;
      console.log(this.option);
    }
  },

  computed:{
      songsToShow(){
        const array = [];
        this.songs.forEach((item)=>{
          if(item.genre.toLowerCase().indexOf(this.option.toLowerCase().trim())>-1){
            array.push(item);
          }
        })
        return array;
      }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    padding: 0px;
    margin: 0px;
    background-color: #1e2d3b;

  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

}
</style>
