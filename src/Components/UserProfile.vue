<template>
  <Header />
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
      <button>Update</button>
      <div class="details">
        <p>Details</p>
        <p>Name - {{ firstName }}{{ lastName }}</p>
        <p>Mobile Number - {{ mobileNo }}</p>
        <p>Email - {{ email }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import Header from "./Header.vue";
import { ref } from "vue";

const firstName = ref("");
const lastName = ref("");
const mobileNo = ref("");
const email = ref("");
</script>
<style>
.userDetails {
  display: flex;
  flex-direction: column;
  width: 100%;
  background-color: black;
  /* border: 1px solid #ddd; */
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
  border-radius: 3px;
  align-items: center;
}
.userDetails-container {
  padding: 20vh;
}
input[type="text"],
input[type="number"],
input[type="email"] {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 3px;
  margin-bottom: 10px;
}
.placeholder {
  width: 600px;
}
.details{
    color: #fff;
}
</style>
