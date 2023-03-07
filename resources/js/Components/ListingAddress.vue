<template>
    <div>
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
defineProps({
    listing: Object,
});
</script>
