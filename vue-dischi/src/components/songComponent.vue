<template>
  <div class="song-container">
    <img :src="info.poster" :alt="info.title">
    <p>{{info.title}}</p>
  </div>
</template>

<script>
export default {
    name:'songComponent',
    props: {
        info: Object,
    },
    
}

console.log(Object);
</script>

<style scoped>

  .song-container{
    width: 100%;
    height: 150px;
    display: flex;
    flex-direction: column;
    padding: 10px 0px;
    background-color: #2e3a46;
  }

  img{
    width: 100%;
    height: 100%;
    margin-bottom: 15px;
  }

  p{
    background-color: #2e3a46;
  }

</style>