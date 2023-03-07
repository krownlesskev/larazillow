<template>
    <div class="mb-4 p-4 flex items-center space-x-4 bg-black">
        <div class="text-amber-100 text-2xl">Luminary Listings</div>
        <Link
            :href="route('listing.index')"
            class="border rounded p-1 border-white hover:bg-white hover:text-black text-white"
            >Listings
        </Link>
        <Link
            :href="route('listing.create')"
            class="border rounded p-1 border-white hover:bg-white hover:text-black text-white"
            >Create Listing
        </Link>
        <div v-if="flash.success" class="bg-lime-600 text-white">
            {{ flash.success }}
        </div>
    </div>
    <slot></slot>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";

defineProps({
    flash: Object,
});
</script>
