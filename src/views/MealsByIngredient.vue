<script setup>
import { onMounted, ref } from "vue"
import axiosClient from "../axiosClient"

const ingredients = ref([])

onMounted(() => {
    axiosClient.get(`list.php?c=list`).then(({ data }) => {
        ingredients.value = data.meals
    })
})
</script>

<template>
    <div v-for="ingredient in ingredients">
        <h3>{{ ingre }}</h3>
    </div>
</template>

