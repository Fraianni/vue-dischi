<template>
    <div>

        <select v-model="selected" @change="$emit('changedGenre', selected)">
            <option disabled value="">Please select one</option>
            <option v-for="(genre,index) in genres " :key="index" :value="genre">
                {{genre}}
            </option>
        </select>

        <button @click="$emit('resetButton', option)">RESET</button>

    </div>
   
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

    methods:{
        reset_button(){
            this.selected='none';
            console.log(this.selected);

        }
    },



}

</script>

<style lang="scss" scoped>
    div{
        display: flex;
    }
    select{
        display: block;
    }

</style>