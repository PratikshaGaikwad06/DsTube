<template>
   <div class="main-body">
    <div class="video-list">
      <VideoCard
        v-for="video in videos"
        :key="video.id"
        :imgSrc="video.imgSrc"
        :title="video.title"
        :views="video.views"
        :channel="video.creator"
        :description="video.desc"
        @remove="removeVideo(video.id)"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import VideoCard from './VideoCard.vue';
import Data from '/src/assets/config/data.json';
const videos = ref(Data);
// const videos = ref([
//   {
//     id: 1,
//     thumbnail: '/src/assets/flower.jpg',
//     title: 'Video Title 1',
//     views: '1,234,567 views',
//     channel: 'Channel Name 1',
//     description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed vehicula bibendum vehicula.',
//   },
//   {
//     id: 2,
//     thumbnail: '/src/assets/flower.jpg',
//     title: 'Video Title 2',
//     views: '987,654 views',
//     channel: 'Channel Name 2',
//     description: 'Nullam scelerisque bibendum euismod. Sed id elit eu odio placerat fringilla ac eget mauris.',
//   },
// ]);
const removeVideo = (videoId) => {
  videos.value = videos.value.filter((video) => video.id !== videoId);
};
</script>

<style scoped>
.main-body {
  width: 100%;
  background-color: black;
}

.video-list {
  display: flex;
  padding: 0px 100px;
  flex-direction: column;
  gap: 20px;
}
</style>