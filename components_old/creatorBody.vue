<script setup lang="ts">
import { ref } from "vue";
import { Month } from "./monthStructure";

const emit = defineEmits({
    update(month: Month) {},
});
const monthNameParts = ref(["", "", ""]);
const selectedDays = ref(0);

function SaveAndUpload() {
    monthNameParts.value.forEach((element) => {
        if (!element) {
            element = "";
        }
    });

    const days = selectedDays.value;
    const fullMonthName: string = `${monthNameParts.value[0] + monthNameParts.value[1] + monthNameParts.value[2]}`;
    const thunder: Month = { month: fullMonthName, days: days };

    console.log("Saving Event Executed");
    emit("update", thunder);
}
</script>

<template>
    <div class="">
        <span>
            <label class="pr-2 align-top">Month</label>
            <select
                size="6"
                v-model="monthNameParts[0]"
                class="mr-1 border w-15"
            >
                <option>j</option>
                <option>nov</option>
                <option>dec</option>
                <option>febr</option>
                <option>m</option>
                <option>sept</option>
            </select>
            <select
                size="6"
                v-model="monthNameParts[1]"
                class="mr-1 border w-15"
            >
                <option>octo</option>
                <option>em</option>
                <option>uly</option>
                <option>a</option>
                <option>une</option>
                <option>an</option>
            </select>
            <select
                size="6"
                v-model="monthNameParts[2]"
                class="mr-1 border w-15"
            >
                <option>ber</option>
                <option>y</option>
                <option>unary</option>
                <option>rch</option>
                <option>pril</option>
                <option>ugust</option>
            </select>
        </span>
    </div>
    <div class="pt-2">
        <span>
            <label class="p-1 pr-5">day</label>
            <input
                type="number"
                class="border p-1 w-10"
                :value="selectedDays"
            />
        </span>
    </div>
    <div class="card-actions justify-end m-2">
        <button class="btn btn-primary" @click="SaveAndUpload()">Save</button>
    </div>
</template>
