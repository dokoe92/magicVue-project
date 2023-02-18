<template>
    <ItemComponent :itemName = "itemName" :closeMod="closeMod"/>
</template>


<script setup>
import ItemComponent from './ItemComponent.vue';
import { ref } from "vue";

const props = defineProps(["itemName","closeMod"]);


</script>


<style scoped>


</style>