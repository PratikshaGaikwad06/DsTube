<template>
   <div class="main-body">
    <div class="video-list">
      <VideoCard
        v-for="video in videos"
        :key="video.id"
        :thumbnail="video.thumbnail"
        :title="video.title"
        :views="video.views"
        :channel="video.channel"
        :description="video.description"
        @remove="removeVideo(video.id)"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import VideoCard from './VideoCard.vue';

const videos = ref([
  {
    id: 1,
    thumbnail: 'https://example.com/thumbnail1.jpg',
    title: 'Video Title 1',
    views: '1,234,567 views',
    channel: 'Channel Name 1',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed vehicula bibendum vehicula.',
  },
  {
    id: 2,
    thumbnail: 'https://example.com/thumbnail2.jpg',
    title: 'Video Title 2',
    views: '987,654 views',
    channel: 'Channel Name 2',
    description: 'Nullam scelerisque bibendum euismod. Sed id elit eu odio placerat fringilla ac eget mauris.',
  },
]);
const removeVideo = (videoId) => {
  videos.value = videos.value.filter((video) => video.id !== videoId);
};
</script>

<style scoped>
.main-body {
  width: 100%;
  margin-top : 60px;
  padding: 20px;
}

.video-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}
</style>