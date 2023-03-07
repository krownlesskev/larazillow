<template>
    <div
        class="border dark:border-white border-black rounded flex flex-col p-4"
    >
        <Price class="text-3xl" :price="listing.price" />

        <span> {{ listing.street_nr }} {{ listing.street }}, </span>
        <span>
            {{ listing.city }}
        </span>
        <ul class="flex justify-center gap-4">
            <li class="text-xl">{{ listing.beds }} bd</li>
            <li class="text-xl">{{ listing.baths }} ba</li>
            <li class="text-xl">{{ listing.area }} sf</li>
        </ul>
    </div>
</template>

<script setup>
import Price from "@/Components/UI/Price.vue";
defineProps({
    listing: Object,
});
</script>
