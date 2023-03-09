<template>
    <div>
        <div class="mb-4 p-4 flex items-center justify-between bg-black">
            <Link
                class="text-amber-100 text-2xl hover:translate-x-3 ease-in-out duration-500"
                :href="route('listing.index')"
                >Luminary Listings</Link
            >
            <Link :href="route('listing.create')" class="btn-primary"
                >Create Listing
            </Link>
        </div>
        <main class="container mx-auto p-4 w-full">
            <div v-if="flash.success" class="flex justify-center">
                <span
                    class="bg-lime-500 font-bold text-white max-w-sm p-2 rounded"
                >
                    {{ flash.success }}
                </span>
            </div>
        </main>
    </div>
    <slot></slot>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";

defineProps({
    flash: Object,
});
</script>
