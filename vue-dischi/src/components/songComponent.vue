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

<style>

</style>