<script setup>
import NavBar from "./NavBar.vue";
</script>

<template>
  <div class="bg-gray-100 h-full">
    <NavBar />
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>
