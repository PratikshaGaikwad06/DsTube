<template>
  <div class="btn">
      DsTube
      <!-- {{ data }} -->
  </div>
</template>

<script setup></script>

<style scoped>
.btn {
    display: flex;
  align-items: center;
  background: red;
  color: white;
  border: none;
  border-radius: 3px;
  /* border: 1px solid #3EA6FF; */
  height: 34px;
  padding: 6px 12px;
  font-size: 16px;
  font-weight: bold;
  justify-content: center;
  cursor: pointer;
  outline: none;
  max-width: 100px;
}

.btn:hover {
  background: darkred; /* Change background color on hover */
}
</style>
