<script setup>
import { ref } from 'vue'

const itemId = ref(0)
const shoppingitem =ref('')
const shoppinglist = ref([])
const shopped = ref(false)



function addItem() {
    shoppinglist.value.push({
        id: itemId.value++,
        item: shoppingitem.value,
        status: shopped.value
    })
}

function removeItem(item) {
    shoppinglist.value = shoppinglist.value.filter(
        (t) => t !== item)
}

</script>


<template>


<div>
    <h1>My To Do List</h1>
    <input type="text" v-model="shoppingitem">
    <button class="buttonstyle" @click="addItem">Add Item</button>
    <ol>

        <li v-for="i in shoppinglist" :key="i.id">
            <input type="checkbox" v-model="i.shopped">

            <span :class="{done: i.shopped}"> {{ i.item }} </span>

            <button @click="removeItem(i)">X</button>

        </li>

    </ol>



</div>




</template>



<style scoped>





</style>