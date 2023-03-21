<script setup>
import { ref, computed, onMounted } from "vue"
import { useRoute } from "vue-router"
import store from "../store"
import MealItem from "../components/MealItem.vue"

const keyWord = ref("")
const meals = computed(() => store.state.searchedMeals)
const route = useRoute()

const searchMeals = () => {
    store.dispatch("searchMeals", keyWord.value)
}

onMounted(() => {
    keyWord.value = route.params.name
    if (keyWord.value) {
        searchMeals()
    }
})
</script>

<template>
    <div class="p-8 pb-0">
        <input
            v-model="keyWord"
            type="text"
            class="rounded border-2 border-gray-400 w-full"
            placeholder="Search for meals..."
            @change="searchMeals"
        />
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
        <MealItem v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
    </div>
</template>
