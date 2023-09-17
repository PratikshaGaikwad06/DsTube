<template>
    <header class="navbar">
      <div class="navbar-container">
        <SubscribeButton />
        <SearchBar />
        <PrimaryButton :title="home"/>
      </div>
    </header>
  </template>
  
  <script setup>
  import SubscribeButton from "./SubscribeButton.vue";
  import SearchBar from "./SearchBar.vue";
  import PrimaryButton from "./PrimaryButton.vue";
  import {ref} from 'vue';
  const home = ref("Home");
  </script>
  
  <style scoped>
  .navbar {
    position: sticky;
    top: 0;
    background-color: #121212;
    color: white;
    padding: 10px 0;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: stretch;
    width: 100%;
    z-index: 100;
  }
  
  .navbar-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
  }
  </style>
  