<template>
    <main>
        <selectComponent :genres="genres" :songs="songs" @changedGenre="choiceOption"/>

       
        <div class="songs-container" v-for="song in songsToShow " :key="song.title">
            <songComponent :info="song"/>
        </div>
    </main>
  
</template>

<script>
import songComponent from './songComponent.vue';
import selectComponent from './selectComponent.vue'


export default {
    name:'mainComponent',

    created(){
    console.log('created')

     this.songs.forEach((item)=>{
        console.log('created')

         if(!(this.genres.includes(item.genre))){
           this.genres.push(item.genre);
         }

        
       })
    
  },
    
    data(){
        return {
            selected:'',
            option:'',
            genres:[],
        };
    },
    
    props:{
        songs: Array,
    },

    components:{
        songComponent,
        selectComponent

    },

    methods:{
    choiceOption(option){
      this.option=option;
      console.log(this.option);
    },
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
      },

      
  }
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