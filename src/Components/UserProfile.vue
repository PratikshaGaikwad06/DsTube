<template>
  <UserProfileHeader />
  <UserProfileBody/>
<!-- 
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
  </div> -->
</template>

<script setup>
import UserProfileHeader from "./UserProfileHeader.vue";
import UserProfileBody from "./UserProfileBody.vue";
</script>

