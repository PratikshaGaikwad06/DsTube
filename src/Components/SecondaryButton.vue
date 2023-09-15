<template>
    <div>
        <button @click="removeVideo" class="remove-button">Remove</button>
    </div>
</template>

<script setup>

</script>

<style scoped>
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