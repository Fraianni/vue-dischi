<template>
  <div id="app">
    <headerComponent/>
    <mainComponent/>
  </div>
</template>

<script>

import axios from 'axios';

import headerComponent from './components/headerComponent.vue'
import mainComponent from './components/mainComponent.vue'


export default {
  name: 'App',
  components: {
    headerComponent,
    mainComponent
    
},
  data() {
    return{
      apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
      songs: [],
      errorMessage:'',
      loading:true,

    };
  },

  created() {
    axios
      .get(this.apiUrl)
      .then(({ status, data }) => {
        this.loading = false;
        if (status === 200) {
          this.songs = data;

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
}
</script>

<style>
  *{
    box-sizing: border-box;
    padding: 0px;
    margin: 0px;
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

}
</style>
