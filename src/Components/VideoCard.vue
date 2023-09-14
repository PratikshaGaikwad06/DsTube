<template>
  <div class="video-card">
    <img :src="thumbnail" alt="Video Thumbnail" class="thumbnail" />
    <div class="video-info">
      <h2 class="video-title">{{ title }}</h2>
      <div class="video-details">
        <p class="channel-name">{{ channel }}</p>
        <p class="views">{{ views }}</p>
      </div>
      <p class="description">{{ description }}</p>
      <button @click="removeVideo" class="remove-button">Remove</button>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  thumbnail: String,
  title: String,
  channel: String,
  views: String,
  description: String,
});

const { emit } = defineEmits();

const removeVideo = () => {
   // emit('remove', videoId);
};
</script>

<style scoped>
.video-card {
  display: block;
  background-color: #fff;
  border: 1px solid #ddd;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  border-radius: 3px;
  overflow: hidden;
  margin: 10px 0;
  max-width: 600px;
}

.thumbnail {
  width: 180px;
  height: 100%;
  object-fit: cover;
}

.video-info {
  padding: 16px;
  flex: 1;
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

.description {
  margin-top: 8px;
  font-size: 14px;
  color: #333;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

.remove-button {
  margin-top: 8px;
  background-color: #ff0000;
  color: #fff;
  border: none;
  border-radius: 3px;
  padding: 6px 12px;
  font-size: 14px;
  cursor: pointer;
  outline: none;
}

.remove-button:hover {
  background-color: #cc0000;
}
</style>
