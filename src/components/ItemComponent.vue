<template>
    <div v-if="itemName === 'Magic Wand'" class="item-container">
        <img src="../../public/images/magic_wand.jpg" alt="">
        <div class="item-description">
            <h2>{{ itemName }}</h2>
            ?? {{ modalOpen }}
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum, odit officiis? Veritatis, minus? Quaerat, dicta molestiae quasi magni commodi illum consequatur similique ea explicabo obcaecati sint hic natus vel ut ipsum consectetur. Repellat odio exercitationem ullam deleniti mollitia nostrum veritatis!</p>
            <ButtonComponent text="Show more" @click="openModal"/>
            <ModalComponent v-if="modalOpen === true" :showModal = "itemName" @changeBool="changeBoolValue" />
        </div>
    </div>
    <div v-if="itemName === 'Magic Broom'" class="item-container">
        <img src="../../public/images/magic_broom.jpg" alt="">
        <div class="item-description">
            <h2>{{ itemName }}</h2>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sit placeat tempore sapiente facere itaque? Suscipit sapiente accusamus saepe, sed, perspiciatis doloremque hic at animi eos, temporibus doloribus! Soluta incidunt minima voluptatem perspiciatis vitae, porro corporis commodi pariatur. Illo, id eaque!</p>
            <ButtonComponent text="Show more" @click="openModal"/>
            <ModalComponent v-if="modalOpen === true" :showModal = "itemName" @changeBool="changeBoolValue" />
        </div>
    </div>
    <div v-if="itemName === 'Magic Cape'" class="item-container">
        <img src="../../public/images/magic_cape.jpg" alt="">
        <div class="item-description">
            <h2>{{ itemName }}</h2>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum, repellendus debitis delectus aliquam perferendis nobis distinctio earum iusto facilis commodi labore. Sint nesciunt, porro quisquam asperiores cumque sapiente quibusdam voluptatibus vero, neque quod consequuntur corporis ratione impedit consequatur! Ducimus, ad.</p>
            <ButtonComponent text="Show more" @click="openModal"/>
            <ModalComponent v-if="modalOpen === true" :showModal = "itemName" @changeBool="changeBoolValue" />
        </div>
    </div>
    <div v-if="itemName === 'Magic Hat'" class="item-container">
        <img src="../../public/images/magic_hat.jpg" alt="">
        <div class="item-description">
            <h2>{{ itemName }}</h2>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellendus quis debitis, illo earum laborum ea neque aliquam similique cum deleniti, quam fugit officia provident unde autem et doloribus necessitatibus quisquam vero animi nostrum accusantium consequatur. Ducimus harum eum quidem rerum.</p>
            <ButtonComponent text="Show more" @click="openModal"/>
            <ModalComponent v-if="modalOpen === true" :showModal = "itemName" @changeBool="changeBoolValue" />
        </div>
    </div>
    <div v-if="itemName === 'Magic Pet'" class="item-container">
        <img src="../../public/images/magic_pet.webp" alt="">
        <div class="item-description">
            <h2>{{ itemName }}</h2>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis, iusto? Tenetur fugiat fugit illum consequuntur, officiis temporibus cumque corrupti quos hic non eveniet aspernatur error nulla expedita recusandae maiores reprehenderit aliquam asperiores soluta cum voluptates beatae magnam iure. Consequuntur, accusantium.</p>
            <ButtonComponent text="Show more" @click="openModal"/>
            <ModalComponent v-if="modalOpen" :showModal = "itemName" @changeBool="changeBoolValue" />
        </div>
    </div>
</template>


<script setup>
    import { ref, watch } from "vue";
    import ButtonComponent from "./ButtonComponent.vue";
    import ModalComponent from "./ModalComponent.vue";
    const props = defineProps(["itemName", "closeMod"]);

    let modalOpen = ref(props.closeMod);
    console.log(modalOpen.value);


    function openModal() {
        if (modalOpen.value) {
            modalOpen.value = false;
            console.log(modalOpen.value)
        } else {
            modalOpen.value = true;
        }
    }

    function changeBoolValue(event)  {
        modalOpen.value = event.value;
    }

    watch(() => props.closeMod, () => {
        console.log("props.closeMod", props.closeMod);
        modalOpen.value = props.closeMod;
        console.log(modalOpen.value);
    })


</script>

<style scoped>
    .item-container {
        display: flex;
        margin-top: 5rem;
    }

    .item-description {
        margin-left: 5rem;
        width: 20rem;
    }

    img {
        height: 20rem;
        width: 20rem;
    }

</style>