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
        margin: 20px;
    }
  .songs-container{
    width: calc(100% / 5 - 40px);
    display: inline-block;
    margin: 20px;
  }
</style>