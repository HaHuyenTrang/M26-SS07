<template>
    <div class="modal" v-if="isOpen">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <h2>{{ title }}</h2>
        <div class="modal-body">
          <slot></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      isOpen: {
        type: Boolean,
        default: false
      }
    },
    methods: {
      closeModal() {
        this.$emit('update:isOpen', false);
      }
    }
  }
  </script>

<style>

</style>