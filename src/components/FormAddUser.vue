
<template>
    <form action="">
      <label for="">Họ và tên</label> <br />
      <input type="text" /> <br />
      <label for="">Email</label><br />
      <input type="text" /> <br />
      <label for="">Địa chỉ</label> <br />
      <input type="text" /><br />
      <button @click="handleClose" type="button">Close</button>
    </form>
  </template>
  
  <script setup>
  const emit = defineEmits("close");
  const handleClose = () => {
    emit("close");
  };
  </script>
  
  <style></style>