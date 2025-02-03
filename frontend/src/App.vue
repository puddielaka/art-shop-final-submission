<script setup>
import { RouterLink, RouterView } from "vue-router";
import Navbar from "./components/Navbar.vue";
import Home from "./views/Home.vue";
</script>

<template>
  <Navbar />

  <RouterView />
</template>
