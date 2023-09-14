<template>
    <div class="search-bar">
        <input
      type="text"
      v-model="query"
      @input="onInputChange"
      placeholder="Search"
    />
    <button @click="search" class="search-button">
      <i class="fa fa-search"></i>
    </button>
  </div>
</template>

<script setup>
</script>

<style scoped>
.search-bar {
  display: flex;
  align-items: center;
  background-color: #121212;
  border: 1px solid #313131;
  border-radius: 2px;
  padding: 6px;
  width: 100%; /* Occupy the full width */
  max-width: 450px;
  height: 34px; /* Set a specific height to match other components */
  flex: 3; /* Adjust the flex property to control the width ratio */

  /* Optional: Adjust margin for spacing between components */
  margin-left: 10px;
  margin-right: 10px;
}

.search-bar input {
  flex-grow: 1;
  border: none;
  padding: 6px;
  font-size: 16px;
  outline: none;
  width: 100%;
  background-color: #121212;
  color: white; /* Change text color to white */
}

.search-bar button.search-button {
  background-color: #121212;
  border: none;
  cursor: pointer;
  outline: none;
  padding: 6px 12px;
  font-size: 16px;
  color: #3EA6FF; /* Change text color to blue */
}

.search-bar button.search-button:hover {
  color: #fff; /* Change text color on hover */
}

</style>