<template>
    <div>
      <!-- c1 dùng props -->
      <button>{{props.title}}</button>
  
      <!-- c2 dùng slots -->
      <!-- B2 : Phát sự kiện thông qua emit -->
      <button @click="handleClick">
        <slot></slot>
      </button>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    title: {
      default: "Click me",
      type: String,
      required: false
    }
  });
  
  // B1 : Khởi tạo ra các emit
  const emit = defineEmits(["onClick"]);
  const handleClick = () => {
    emit("onClick", "Hello");
  };
  </script>
  
  <style>
  </style>