<template>
    <main>
        <div v-for="song in songs " :key="song.title">
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

<style>

</style>