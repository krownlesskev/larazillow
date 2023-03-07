<template>
    <div class="flex flex-col-reverse md:grid md:grid-cols-12 gap-4 m-4">
        <div
            class="col-span-12 md:col-span-7 border border-black dark:border-white flex items-center w-full"
        >
            <span class="w-full text-center font-medium text-gray-500">
                No Images
            </span>
        </div>
        <div class="md:col-span-5 flex flex-col gap-4">
            <ListingAddress :listing="listing" />
            <div
                class="border p-4 dark:border-white border-black w-full text-center"
            >
                Make an Offer
            </div>
        </div>
    </div>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
import ListingAddress from "../../Components/ListingAddress.vue";

defineProps({
    listing: Object,
});
</script>

<script>
import MainLayout from "../../Layouts/MainLayout.vue";

export default {
    layout: MainLayout,
};
</script>
