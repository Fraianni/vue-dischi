<template>
   <select v-model="selected" @change="$emit('changedGenre', selected)">
            <option disabled value="">Please select one</option>
            <option v-for="(genre,index) in genres " :key="index" :value="genre">
                {{genre}}
            </option>
        </select>
</template>

<script>
export default {
    name:'selectComponent',
   

    data(){
        return {
            selected:'',
            option:'',
            
        };
    },

    props:{
        songs: Array,
        genres: Array,

    },



}

</script>

<style scoped>
    select{
        display: block;
    }

</style>