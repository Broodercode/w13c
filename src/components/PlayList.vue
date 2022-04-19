<template>
    <div class="song-box">
<p>Play List</p>
<p class="song-title">{{title}}</p>
<p class=song-artist>{{artist}}</p>
    </div>
</template>

<script>
    export default {
        name: "PlayList",
           props: ['title', 'artist']
    }
</script>

<style scoped>
.song-box{
    display: block;
   border: 1px solid red; 
   width: 100%;
   height: 100%;
}
</style>