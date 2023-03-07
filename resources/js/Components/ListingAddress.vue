<template>
    <div class="flex flex-col">
        <span class="text-amber-500 dark:text-amber-100 sm:text-2xl"
            >${{ listing.price }}</span
        >
        <span> {{ listing.street_nr }} {{ listing.street }}, </span>
        <span>
            {{ listing.city }}
        </span>
        <ul class="flex justify-evenly">
            <li>{{ listing.beds }} bd</li>
            <li>{{ listing.baths }} ba</li>
            <li>{{ listing.area }} sf</li>
        </ul>
    </div>
</template>

<script setup>
defineProps({
    listing: Object,
});
</script>
