<script setup>
import YoutubeButton from "../components/YoutubeButton.vue"

const { meal } = defineProps({
    meal: Object,
})
</script>

<template>
    <div class="bg-white shadow rounded-xl">
        <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
            <img
                :src="meal.strMealThumb"
                :alt="meal.strMeal"
                class="rounded-t-xl h-48 w-full object-cover"
            />
        </router-link>

        <div class="p-5">
            <h3 class="font-bold">{{ meal.strMeal }}</h3>
            <p class="mb-4">
                Lorem ipsum dolor sit amet consectetur, adipisicing elit. At
                totam qui impedit saepe inventore. Omnis eos dolor, molestias
                alias at consectetur eligendi animi nam ab excepturi. Ea
                corrupti placeat natus!
            </p>
            <div class="flex items-center justify-between">
                <YoutubeButton :href="meal.strYoutube" />
            </div>
        </div>
    </div>
</template>
