<script setup lang="ts">
import CreatorBody from "./componets/creatorBody.vue";
import Navbar from "./componets/navbar.vue";
// import { invoke } from "@tauri-apps/api/core";

// const _greetMsg = ref("");
// const _name = ref("");
</script>

<template>
    <link href="/src/app.css" rel="stylesheet" />
    <div>
        <Navbar />
        <div class="card bg-base-100 w-96 shadow-sm">
            <div class="card-body">
                <h1 class="card-title">Creator</h1>
                <CreatorBody />
            </div>
        </div>
    </div>
</template>
