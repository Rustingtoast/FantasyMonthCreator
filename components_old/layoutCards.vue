<script setup lang="ts">
import CreatorBody from "./creatorBody.vue";
import MonthListing from "./monthListing.vue";
import YearSilder from "./yearSlider.vue";
import { Month } from "./monthStructure.ts";
import { ref } from "vue";

let selctedYear = ref(0);
let monthCollection = ref([{} as Month]);

function savingMonthEntry(addedMonth: Month) {
    monthCollection.value.push(addedMonth);
}
</script>
<template>
    <div class="flex justify-center">
        <div class="card bg-base-100 w-96 shadow-sm p-2">
            <div class="card-title">Creator</div>
            <YearSilder v-model="selctedYear" />
            <div class="divider"></div>
            <CreatorBody @update="(e: Month) => savingMonthEntry(e)" />
            </div>

                <div class="card bg-base-100 w-96 shadow-sm pl-2">
                    <div class="card-body">
                        <div class="card-title">Year {{ selctedYear }}</div>
                            <MonthListing v-model="monthCollection" />
                        </div>
                        <div class="card-actions justify-end m-2">
                            <button disabled class="btn btn-primary">Export</button>
                        </div>
                    </div>
                </div>
            
</template>