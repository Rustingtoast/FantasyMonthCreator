<script setup>
const model = defineModel({ default: 0 });
</script>

<template>
    <span>
        <label class="pr-5">Year</label>
        <input
            v-model="model"
            type="text"
            class="border border-slate-500 p-1 w-30"
        />
        <input
            type="range"
            class="block p-2 w-full"
            min="-100000"
            max="100000"
            v-model="model"
        />
    </span>
</template>
