<template>
    <div>
      <h2>List User</h2>
      <button @click="handleOpen">Add User</button>
      <div v-if="isOpen">
        <FormAddUser @close="handleClose" />
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  let isOpen = ref(false);
  
  import FormAddUser from "./FormAddUser.vue";
  const handleOpen = () => {
    isOpen.value = true;
  };
  
  const handleClose = () => {
    isOpen.value = false;
  };
  </script>
  
  <style></style>
  