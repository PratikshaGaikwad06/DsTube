<template>
  <div class="video-card">
    <img :src="imgSrc" alt="Video Thumbnail" class="thumbnail" />
    <div class="video-info">
      <h2 class="video-title">{{ title }}</h2>
      <h5 class="views">{{ views }}</h5>
      <div class="video-details">
        <p class="channel-name">{{ channel.firstname }} {{ channel.lastname }}</p>
        <!-- <p class="views">{{ views }}</p> -->
      </div>
      <p class="description">{{ description }}</p>
      <SecondaryButton/>
      <!-- <button @click="removeVideo" class="remove-button">Remove</button> -->
    </div>
  </div>
</template>

<script setup>
import SecondaryButton from './SecondaryButton.vue';
defineProps({
  imgSrc: String,
  title: String,
  channel: Object,
  views: String,
  description: String,
});

defineEmits();

const removeVideo = () => {
   // emit('remove', videoId);
};
</script>

<style scoped>
.video-card {
  display: flex;
  background-color: black;
  border: 1px solid;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  border-radius: 3px;
  overflow: hidden;
  /* max-width: 1850px; */
  margin: 60px;
}

.thumbnail {
  flex : 0 0 auto;
  overflow: hidden;
  /* width: 180px; */
  /* width: 250px; */
  height: 250px;
  /* height: 100%; */
  object-fit: cover;
}

.video-info {
  padding: 16px;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.video-title {
  color: #fff;
  font-size: 25px;
  font-weight: bold;
  margin: 0;
}

.video-details {
  display: flex;
  margin-top: 8px;
  color: #fff;
  font-size: 14px;
}

.channel-name {
  margin-right: 8px;
}

.views {
  color: #fff;
  margin: 1px;
  /* flex-grow: 1; */
}

.description {
  margin-top: 8px;
  font-size: 14px;
  color: #fff;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

.remove-button {
  margin-top: 8px;
  max-width: 100px;
  background-color: black;
  color: #fff;
  border: 1px solid white;
  border-radius: 3px;
  padding: 6px 12px;
  font-size: 14px;
  cursor: pointer;
  outline: none;
}

.remove-button:hover {
  background-color: grey;
}
</style>
