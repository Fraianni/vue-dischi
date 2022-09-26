<template>
    <main>
        <div class="songs-container" v-for="song in songs " :key="song.title">
            <songComponent :info="song"/>
        </div>
    </main>
  
</template>

<script>
import songComponent from './songComponent.vue';

export default {
    name:'mainComponent',
    
    props:{
        songs: Array
    },

    components:{
        songComponent,
    }
}



</script>

<style scoped>
    main{
    }
  .songs-container{
    width: calc(100% / 5 - 40px);
    height: 300px;
    display: inline-block;
    margin: 50px 20px;
    padding: 20px;
  
    color: white;
    background-color: #2e3a46;
  }
</style>