<template>
  <div >
    <button class="primary-btn" @click="btnClickEvent">{{ title }}</button>
      <!-- Profile -->
      <!-- {{ title }} -->
      <!-- {{ data }} -->
  </div>
</template>

<script setup>
defineProps({
  title : String
});
const emit = defineEmits(['btn-click-event']);
const btnClickEvent=()=>{
    emit('btn-click-event', true);
}
</script>

<style scoped>
.primary-btn {
    margin-left: 6px;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 34px;
  max-width: 100px;
  border: 1px solid #3EA6FF;
  font-size: 16px;
  color: #3EA6FF;
  background-color: #121212;
  cursor: pointer;
  outline: none;
  border-radius: 3px;
  flex: 1;
  }
  
  .primary-btn:hover {
    background-color: #3EA6FF; /* Change background color on hover */
    color: #121212; /* Change text color on hover */
  }
</style>
