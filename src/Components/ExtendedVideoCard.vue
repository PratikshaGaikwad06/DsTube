<template>
  <div class="extended-video-card">
    <div class="extended-video-card-container">
      <img :src="videos[0].thumbnail" alt="Video Thumbnail" class="thumbnail" />

      <div class="video-info">
        <h2 class="video-title">{{ videos[0].title }}</h2>
        <div class="video-details">
          <p class="channel-name">{{ videos[0].channel }}</p>
          <p class="views">{{ videos[0].views }} views</p>
        </div>
        <!-- <h2 class="video-title">{{ title }}</h2>
    <h5 class="views">{{ views }}</h5>
   // trending, popular 
    <p class="channel-name">{{ channel }}</p> -->
      </div>
      <div class="video-actions">
        <SecondaryButton />
        <SecondaryButton />
        <SecondaryButton />
      </div>
      <div class="comment-section">
        <input type="text" @input="onInputChange" placeholder="Add a comment" />
      </div>
    </div>
  </div>
</template>

<script setup>
import SecondaryButton from "./SecondaryButton.vue";
import { ref } from 'vue';
import Data from '/src/assets/config/data.json';
const videos = ref([
  {
    id: 1,
    thumbnail: '/src/assets/flower.jpg',
    title: 'Video Title 1',
    views: '1,234,567 views',
    channel: 'Channel Name 1',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed vehicula bibendum vehicula.',
  },
  {
    id: 2,
    thumbnail: '/src/assets/flower.jpg',
    title: 'Video Title 2',
    views: '987,654 views',
    channel: 'Channel Name 2',
    description: 'Nullam scelerisque bibendum euismod. Sed id elit eu odio placerat fringilla ac eget mauris.',
  },
]);
// const videos = ref([
//     {
//         "id": "1",
//         "imgSrc": "https://i.ytimg.com/vi/t0Q2otsqC4I/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCFcrz2zM6mPUmJiCsC7c7suOzSug",
//         "title": "Tom & Jerry | Tom & Jerry in Full Screen | Classic Cartoon Compilation | WB Kids by WB Kids",
//         "views": 20078574,
//         "desc": "Did you know that there are only 25 classic Tom & Jerry episodes that were displayed in a widescreen CinemaScope from the 1950s? Enjoy a compilation filled with some of the best moments from these full screen episodes!",
//         "creator": {
//             "firstname": "WB",
//             "lastname": "Kids"
//         },
//         "isHidden": false
//     },
//     {
//         "id": "2",
//         "imgSrc": "https://i.ytimg.com/vi/5NG7sVcB0QQ/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLD0hHqg6BjpbqR1UHl10IznPfmLzw",
//         "title": "Tom and Jerry 2018 | 2 Fast 2 Furious + Tom and Jerry in Hospital",
//         "views": 9174395,
//         "desc": "Did you know that there are only 25 classic Tom & Jerry episodes that were displayed in a widescreen CinemaScope from the 1950s? Enjoy a compilation filled with some of the best moments from these full screen episodes! ",
//         "creator": {
//             "firstname": "WB",
//             "lastname": "Kids"
//         },
//         "isHidden": false
//     }
//   ]);
</script>

<style scoped>
.extended-video-card {
  display: flex;
  flex-direction: column;
  width: 100%;
  background-color: #fff;
  /* border: 1px solid #ddd; */
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  border-radius: 3px;
  /* padding: 16px; */
  /* margin: 10px; */
  /* max-width: 600px;*/
}

.extended-video-card-container {
  padding: 20vh;
}
.thumbnail {
   width: 100%;
  /*height: auto;
  max-height: 300px; */
  height: 80vh;
  object-fit: cover;
}

.video-info {
  margin-top: 16px;
}

.video-title {
  font-size: 18px;
  font-weight: bold;
  margin: 0;
}

.video-details {
  display: flex;
  margin-top: 8px;
  color: #666;
  font-size: 14px;
}

.channel-name {
  margin-right: 8px;
}

.views {
  flex-grow: 1;
}

.video-actions {
  display: flex;
  margin-top: 16px;
}

.comment-section {
  margin-top: 16px;
}

textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 3px;
  resize: vertical;
  margin-bottom: 10px;
}
</style>
