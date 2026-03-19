<script setup lang="ts">
import { Month } from "./monthStructure.ts";

let model = defineModel<Month[]>({ required: true });

function Remove(index: number) {}
</script>

<template>
    <div class="overflow-auto h-full w-full">
        <table class="table table-xs table-pin-rows table-pin-cols">
            <thead>
                <tr>
                    <th>Nr</th>
                    <td>Name</td>
                    <td>Days</td>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(month, index) in model">
                    <th>{{ index }}</th>
                    <td>{{ month.month }}</td>
                    <td>{{ month.days }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
