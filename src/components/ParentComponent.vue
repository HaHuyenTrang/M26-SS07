<template>
  <div>
    <h1>Parent component</h1>
    <ChildrenComponent
      :userNameProps="userName"
      :ageProps="userAge"
      :userInfoProps="userInfo"
      :infoComponentProps="infoComponent"
      :productProps="product"
      :countProps="count"
      :idProps="id"
    />
    <h3>toi la: {{ userName }} - nam nay: {{ userAge }} tuoi</h3>
    <h2>
      id: {{ userInfo.id }} - ten: {{ userInfo.name }} - tuoi:
      {{ userInfo.age }}
    </h2>
    <h1>BÀI 1</h1>
    <h1>PARENT COPONENT: {{ infoComponent }}</h1>
    <h1>CHILDRENT COMPONENTS: {{ infoComponent }}</h1>
    <h1>BÀI 2</h1>
    <h1>SAN PHAM: {{ product }}</h1>
    <h1>BÀI 3</h1>
    <button @click="handleCount">Increment</button>
    <h1>COUNT: {{ count }}</h1>
    <h1>BÀI 4</h1>
    <button @click="handleDelete">Delete</button>
    <h1>
      ID TO DELETE: <H2 v-show="show">{{ id }}</H2>
    </h1>
    <h1>BÀI 5</h1>
    <div class="modal" v-if="isOpen">
      <div class="modal-content">
        <span class="close" @click="closeModal">&times;</span>
        <h2>{{ title }}</h2>
        <div class="modal-body">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, vShow } from "vue";
import ChildrenComponent from "./ChildrenComponent.vue";
const userName = "Ha Huyen Trang ";
// bien tuoi, truyen tu parent xuong childrent
const userAge = 19;
const userInfo = {
  id: 1,
  name: "HHT",
  age: 19,
};
const product = {
  id: 1,
  productName: "buoi ba roi",
  price: 12,
  quantity: 10,
};
const infoComponent = "Rikkeiacademy";
const count = ref(0);
const handleCount = () => {
  count.value++;
  // console.log(count);
};
const id = 1;
const show = ref(false);
const handleDelete = () => {
  show.value = !show.value;
};

const Modal = {
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

<style></style>
