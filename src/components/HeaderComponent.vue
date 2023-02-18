<template>
    <h1>Magic Vue Shop</h1>
    <ButtonComponent @update="update" item-name="Magic Wand"/>
    <ButtonComponent @update="update" item-name="Magic Broom" />
    <ButtonComponent @update="update" item-name="Magic Cape" />
    <ButtonComponent @update="update" item-name="Magic Hat" />
    <ButtonComponent @update="update" item-name="Magic Pet" />

</template>


<script setup>
import ButtonComponent from './ButtonComponent.vue';

const emit = defineEmits(["update"])



function update(event) {
    emit("update", event)
}

</script>


<style scoped>


</style>