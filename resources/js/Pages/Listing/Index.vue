<template>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 m-4">
        <Listing
            v-for="(listing, index) in listings"
            :key="listing.id"
            :listing="listing"
        />
    </div>
</template>

<script setup>
import Listing from "@/Pages/Listing/Index/Components/Listing.vue";
defineProps({
    listings: Array,
});
</script>
