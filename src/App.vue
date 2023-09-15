<template>
  <div class="main-container">
    <!-- <Header/>
    <MainBody/>  -->
    <Home/>
    <View/>
    <UserProfile/>
  </div>
</template>

<script setup>
import MainBody from "./Components/MainBody.vue";
import Home from "./Components/Home.vue";
import View from "./Components/View.vue";
import UserProfile from "./Components/UserProfile.vue";

</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap");

body {
  margin: 0px;
  height: 100vh;
  font-family: "Roboto", sans-serif;
}

#app {
  height: 100%;
}

.main-container {
  /* height: 100%; */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
