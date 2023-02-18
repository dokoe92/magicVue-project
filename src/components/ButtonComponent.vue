<template>
    <button @click="emitItem">{{ itemName || text}}</button>

</template>


<script setup>
    import { ref } from "vue";
    const props = defineProps(["itemName", "text"]);
    const name = ref(props.itemName)
    const bool = ref(false);
    const emit = defineEmits(["update", "showMore"]);

    function emitItem() {
        emit("update", {
            name: props.itemName,
            closeModal: false})
    }

    


</script>


<style scoped>


</style>