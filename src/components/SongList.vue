<template>
    <div class="song-box">
<p>Song List</p>
<p class="song-title">{{title}}</p>
<p class=song-artist>{{artist}}</p>
    </div>
</template>

<script>
    export default {
        name: "SongList",
        props: ['title', 'artist']
      
    }
</script>

<style scoped >
.song-box{
    display: block;
   border: 1px solid black; 
   width: 100%;
   height: 100%;
}
</style>