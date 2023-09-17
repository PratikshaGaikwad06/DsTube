<template>
  <div class="extended-video-card">
    <div class="extended-video-card-container">
      <img :src="videos[0].thumbnail" alt="Video Thumbnail" class="thumbnail" />

      <div class="video-info">
        <h2 class="video-title">{{ videos[0].title }}</h2>
        <div class="video-details">
          <p class="views">{{ formattedViews }} views</p>
          <p v-if="likesCount > 10 && likesCount <= 15" class="tag popular">Popular</p>
          <p v-if="likesCount > 15" class="tag trending">Trending</p>
        </div>
        <!-- <h2 class="video-title">{{ title }}</h2>
    <h5 class="views">{{ views }}</h5>
   // trending, popular  
   <p class="channel-name">{{ channel }}</p> -->
      <p class="channel-name">{{ videos[0].creator.firstname }} {{ videos[0].creator.lastname }}</p>
   
      </div>
      <div class="video-actions">
        <SecondaryButton class="btn" @btn-click-event="btnClick('like')" :title="buttonTitle" />
        <SecondaryButton class="btn" v-if="likesCount > 0" @btn-click-event="btnClick('dislike')" :title="dislike"/>
        <SecondaryButton class="btn" :title="share"/>
      </div>
      <div class="comment-section">
        <input type="text" @input="onInputChange" placeholder="Add a comment" />
      </div>
    </div>
  </div>
</template>

<script setup>
import SecondaryButton from "./SecondaryButton.vue";
import { ref,computed } from 'vue';
import Data from '/src/assets/config/data.json';
const dislike = ref("Dislike");
const share = ref("Share");
const videos = ref([
{
        "id": "1",
        "thumbnail": "https://i.ytimg.com/vi/t0Q2otsqC4I/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCFcrz2zM6mPUmJiCsC7c7suOzSug",
        "title": "Tom & Jerry | Tom & Jerry in Full Screen | Classic Cartoon Compilation | WB Kids by WB Kids",
        "views": 20078574,
        "desc": "Did you know that there are only 25 classic Tom & Jerry episodes that were displayed in a widescreen CinemaScope from the 1950s? Enjoy a compilation filled with some of the best moments from these full screen episodes!",
        "creator": {
            "firstname": "WB",
            "lastname": "Kids"
        },
        "isHidden": false
    }
  // {
  //   id: 1,
  //   thumbnail: 'https://i.ytimg.com/vi/t0Q2otsqC4I/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLCFcrz2zM6mPUmJiCsC7c7suOzSug',
  //   title: 'Video Title 1',
  //   views: '1,234,567 views',
  //   channel: 'Channel Name 1',
  //   description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed vehicula bibendum vehicula.',
  // }
]);
let likesCount = ref(0);
// const btnClick = (likes) =>{
//   likesCount.value = likes;
//   console.log(likesCount.value);
// }

const btnClick = (action) => {
  if (action === 'like') {
    likesCount.value++;
  } else if (action === 'dislike') {
    likesCount.value--;
  }
}


const buttonTitle =  computed(() => `Like ${likesCount.value}`);

const formatNumber = (value) => {
  return value.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
};

const formattedViews = computed(() => {
  if (videos.value.length > 0) {
    return formatNumber(videos.value[0].views);
  }
  return '';
});
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
  justify-content: center;
  /* flex-direction: column; */
  width: 100%;
  background-color: black;
  /* border: 1px solid #ddd; */
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  border-radius: 3px;
  /* padding: 16px; */
  /* margin: 10px; */
  /* max-width: 600px;*/
}

.extended-video-card-container {
  padding: 5vh;
}
.thumbnail {
   /* width: 100%; */
  /*height: auto;
  max-height: 300px; */
  height: 60vh;
  object-fit: cover;
}

.video-info {
  margin-top: 16px;
}

.video-title {
  font-size: 18px;
  color: white;
  font-weight: bold;
  margin: 0;
}

.video-details {
  display: flex;
  margin: 0px 8px 0px 0px;
  color: #fff;
  font-size: 13px;
}
.video-actions .btn{
  
  margin: 10px;
  margin-left: 0;
}
.channel-name {
  margin: 8px 8px 0px 0px;
  color: #fff;
  font-weight: 900;
}

.views {
  margin-right: 8px;
}

.tag {
  font-weight: bold;
  /* padding: 2px 6px; */
  /* border-radius: 4px; */
}

.popular {
  /* background-color: red; */
  color: red;
}

.trending {
  /* background-color: green; */
  color: green;
}
.video-actions {
  display: flex;
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
