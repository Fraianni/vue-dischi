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
        background-color: grey;
        display: flex;
        justify-content: start;
        
    }
    img{
        width: 4%;
        margin-left: 5px;
        
    }

</style>