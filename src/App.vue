<script setup lang="ts">
import Navbar from "./components/navbar.vue";
import LayoutCards from "./components/layoutCards.vue";
// import { invoke } from "@tauri-apps/api/core";


</script>

<template>
    <link href="/src/app.css" rel="stylesheet" />
    <div class="mb-2">
        <Navbar />
    </div>
    <LayoutCards />
    
</template>
