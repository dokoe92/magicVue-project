<script setup>
import BodyComponent from './components/BodyComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import { ref } from "vue";

const item = ref("");
const closeModal = ref("");

function setItem(event) {
  item.value = event.name;
  closeModal.value = event.closeModal;
}


</script>

<template>
  <HeaderComponent @update="setItem"/>
  <BodyComponent :itemName="item" :closeMod="closeModal" />
  <FooterComponent />

</template>

<style scoped>

</style>
