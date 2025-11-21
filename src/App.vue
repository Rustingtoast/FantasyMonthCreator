<script setup lang="ts">
import CreatorBody from "./components/creatorBody.vue";
import Navbar from "./components/navbar.vue";
import MonthListing from "./components/monthListing.vue";
import YearSilder from "./components/yearSlider.vue";
import { Month } from "./components/monthStructure.ts";
import { ref } from "vue";
// import { invoke } from "@tauri-apps/api/core";

let selctedYear = ref(0);
let monthCollection = ref([{} as Month]);

function savingMonthEntry(addedMonth: Month) {
    monthCollection.value.push(addedMonth);
}
</script>

<template>
    <link href="/src/app.css" rel="stylesheet" />
    <div class="mb-2">
        <Navbar />
    </div>
    <div class="flex justify-center">
        <div class="card bg-base-100 w-96 shadow-sm p-2">
            <div class="card-title">Creator</div>
            <YearSilder v-model="selctedYear" />
            <div class="divider"></div>
            <CreatorBody @update="" />
        </div>

        <div class="card bg-base-100 w-96 shadow-sm pl-2">
            <div class="card-body">
                <div class="card-title">Year {{ selctedYear }}</div>
                <MonthListing />
            </div>
            <div class="card-actions justify-end m-2">
                <button class="btn btn-primary">Export</button>
            </div>
        </div>
    </div>
</template>
