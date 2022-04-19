<template>
  <div class="main">
    <div class="song-box">
      <h1>Song List</h1>

      <div
        v-for="(song, index) in songArr"
        :key="index"
        @click="onSongClick(index)"
      >
        <SongList v-bind:title="song.title" v-bind:artist="song.artist" />
      </div>
    </div>
    <div class="play-box">
      <h1>Play List</h1>
      <div
        v-for="(song, index) in playArr"
        :key="index + 'X'"
        @click="onPlayClick(index)"
      >
        <PlayList v-bind:title="song.title" v-bind:artist="song.artist" />
      </div>
    </div>
  </div>
</template>

<script>
import SongList from "./SongList.vue";
import PlayList from "./PlayList.vue";
export default {
  name: "PageBody",
  components: { SongList, PlayList },
  data() {
    return {
      songArr: [
        {
          title: "track01",
          artist: "artist01",
          id: 0,
        },
        {
          title: "track02",
          artist: "artist01",
          id: 1,
        },
        {
          title: "track03",
          artist: "artist01",
          id: 2,
        },
        {
          title: "track04",
          artist: "artist02",
          id: 3,
        },
        {
          title: "track05",
          artist: "artist03",
          id: 4,
        },
        {
          title: "track06",
          artist: "artist04",
          id: 5,
        },
        {
          title: "track07",
          artist: "artist05",
          id: 6,
        },
      ],
      playArr: [],
    };
  },
  methods: {
    onSongClick(index) {
      let songPick = this.songArr.splice(index, 1);
      this.playArr.push(songPick[0]);
    },
    onPlayClick(index) {
      let playPick = this.playArr.splice(index, 1);

      this.songArr.push(playPick[0]);
    },
  },
};
</script>

<style scoped>
.main {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}

.song-box {
  padding: 10px;
}
.play-box {
  padding: 10px;
}
</style>
