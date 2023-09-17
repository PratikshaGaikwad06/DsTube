<template>
  <div>
    <button class="button" @click="btnClick">{{ title }}</button>
    <!-- <button @click="removeVideo" class="remove-button">{{title}}</button> -->
  </div>
</template>

<script setup>
import { ref} from "vue";
defineProps({
  title: String,
});


const emit = defineEmits(["btn-click-event"]);
const btnClick = () => {
    emit("btn-click-event");
};

// const btnClick = computed(() => {
//   if (title.toLowerCase() === "dislike") {
//     count.value--;
//   } else if (title.substring(0, 4).toLowerCase() === "like") {
//     count.value++;
//   }
//   emit("btn-click-event", count.value);
// });

</script>

<style scoped>
.button {
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
