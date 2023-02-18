<template>
    <div class="modal-container">
        <h1>{{ showModal }}</h1>
        <p>ABRAKADABRA</p>
        <ButtonComponent text="Close" @click="closeModal"/>
    </div>
</template>

<script setup>
import ButtonComponent from './ButtonComponent.vue';

    const props = defineProps(["showModal"])
    const emits = defineEmits(["changeBool"])

    function closeModal() {
        document.querySelector(".modal-container").style.display = "none";
        emits("changeBool", false)
    }

</script>

<style scoped>
    .modal-container {
        width: 20rem;
        height: 20rem;
        border: 1px solid black;
        position: fixed;
        top: 5rem;
        background-color: gray;
    }

</style>