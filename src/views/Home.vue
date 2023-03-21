<script setup>
import { onMounted, ref } from "vue"
import axiosClient from "../axiosClient.js"

const ingredients = ref([])

onMounted(async () => {
    const res = await axiosClient.get("/list.php?i=list")
    ingredients.value = res.data
})
</script>

<template></template>
