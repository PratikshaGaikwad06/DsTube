<template>
  <div class="main-container">
    <Header/>
    <!-- <div style="height: 1000px;">Your page content here</div> -->
    <MainBody/>
  </div>
</template>

<script setup>
import Header from "./Components/Header.vue";
import MainBody from "./Components/MainBody.vue";
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
