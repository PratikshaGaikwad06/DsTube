<template>
  <div class="userDetails">
    <div class="userDetails-container">
      <input
        type="text"
        placeholder="First Name"
        v-model="firstName"
      /><br /><br />
      <input
        type="text"
        placeholder="Last Name"
        v-model="lastName"
      /><br /><br />
      <input
        type="number"
        placeholder="Mobile Number"
        v-model="mobileNo"
      /><br /><br />
      <input type="email" placeholder="Email" v-model="email" /><br /><br />

      <div class="updateBtn">
        <PrimaryButton :title="update" />
      </div>

      <div class="details">
        <p>Details</p>
        <p>Name - {{ fullName }}</p>
        <p>Mobile Number - {{ mobileNo }}</p>
        <p>Email - {{ email }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import PrimaryButton from "./PrimaryButton.vue";
import { ref,computed } from "vue";

const firstName = ref("");
const lastName = ref("");
const mobileNo = ref("");
const email = ref("");
const fullName = computed(() => {
  return `${firstName.value} ${lastName.value}`;
});

const update = ref("Update");
</script>

<style scoped>
.userDetails {
  display: flex;
  flex-direction: column;
  width: 100%;
  background-color: black;
  /* border: 1px solid #ddd; */
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  border-radius: 3px;
  justify-content: center;
  /* align-items: center; */
}
.userDetails-container {
  display: flex;
  flex-direction: column;
  margin: 0vh  50vh;
  padding: 20vh;
}
input[type="text"],
input[type="number"],
input[type="email"] {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  background-color: black;
  color: #fff;
  border-radius: 3px;
  margin-bottom: 10px;
  object-fit: cover;
}
.updateBtn {
  display: flex;
  justify-content: center;
}
.details {
  font-size: 16px;
  color: #fff;
}

input::placeholder {
  font-weight: 200;
  color: #fff;
}
</style>
