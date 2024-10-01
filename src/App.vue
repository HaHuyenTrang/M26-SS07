<template>
  <div>
    <h1>Home Page</h1>

    <ParentComponent />

    <BaseButton></BaseButton>
    <BaseButton title="Add product"></BaseButton>
    <SlotComponent>
      <!-- Nội dung này chính là slot sau này dùng -->
      <a href>Face book</a>
    </SlotComponent>

    <BaseButton @onClick="handleClickParent">Click me</BaseButton>
      <Card>
       
        <template #header>
          Thông tin sản phẩm
        </template>
        <template #body>
          Đây là mô tả ngắn gọn về sản phẩm này. Sản phẩm có các tính năng nổi bật và giá cả hợp lý.
        </template>

        <template #footer>
         <button> Xem chi tiết</button>
        </template>
      </Card>
      <Listuser/>
  </div>
 </template >

<script setup>
import ParentComponent from "./components/ParentComponent.vue";
import BaseButton from "./components/BaseButton.vue";
import SlotComponent from "./components/SlotComponent.vue";
import Card from "./components/Card.vue";
import Listuser from "./components/Listuser.vue";

const handleClick = () => {
  console.log("Clicked");
};

const handleClickParent = data => {
  console.log("Dữ liệu truyền từ con : ", data);
};
</script>

<style>
</style>