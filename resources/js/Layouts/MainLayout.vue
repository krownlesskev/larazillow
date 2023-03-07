<template>
    <div class="mb-4 p-4 flex items-center justify-between bg-black">
        <Link
            class="text-amber-100 text-2xl hover:translate-x-3 ease-in-out duration-500"
            :href="route('listing.index')"
            >Luminary Listings</Link
        >
        <Link
            :href="route('listing.create')"
            class="rounded p-1 bg-amber-100 hover:bg-amber-200 text-black hover:scale-110 ease-in-out duration-500"
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
