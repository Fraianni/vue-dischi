<template>
    <header>
        <img src="https://upload.wikimedia.org/wikipedia/commons/8/84/Spotify_icon.svg" alt="">
    </header>
  
</template>

<script>
export default {
    name:'headerComponent'
}
</script>

<style scoped>
    header{
        height: 15vh;
        background-color: #2e3a46;
        display: flex;
        justify-content: flex-start;
 
        
    }
    img{
        width: 50px;
        margin-left: 5px;
        background-color: #2e3a46;

    }

</style>