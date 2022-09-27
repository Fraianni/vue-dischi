<template>
    <main>
        <select v-model="selected" @change="$emit('changedGenre', selected)">
            <option disabled value="">Please select one</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
        <div class="songs-container" v-for="song in songs " :key="song.title">
            <songComponent :info="song"/>
        </div>
    </main>
  
</template>

<script>
import songComponent from './songComponent.vue';

export default {
    name:'mainComponent',
    
    data(){
        return {
            selected:'',
        };
    },
    
    props:{
        songs: Array
    },

    components:{
        songComponent,
    },

    methods:{
       
    },
}



</script>

<style scoped>
   
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