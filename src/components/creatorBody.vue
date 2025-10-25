<script setup>
import monthListing from "../componets/monthListing.vue";
</script>

<template>
    <div class="">
        <span>
            <label class="pr-2 align-top">Month</label>
            <select size="6" class="mr-1 border w-15">
                <option>j</option>
                <option>nov</option>
                <option>dec</option>
                <option>febr</option>
                <option>m</option>
                <option>sept</option>
            </select>
            <select size="6" class="mr-1 border w-15">
                <option>octo</option>
                <option>em</option>
                <option>uly</option>
                <option>a</option>
                <option>une</option>
                <option>an</option>
            </select>
            <select size="6" class="mr-1 border w-15">
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
            <input type="number" class="border p-1 w-10" value="0" />
        </span>
    </div>
</template>
