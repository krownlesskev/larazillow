<template>
    <div class="grid grid-cols-1 sm:grid-cols-3">
        <div
            v-for="(listing, index) in listings"
            :key="listing.id"
            class="border dark:border-white border-black rounded w-auto flex flex-col p-4 m-4 hover:scale-105 ease-in-out duration-500"
        >
            <div>
                <Link :href="route('listing.show', { listing: listing.id })">
                    <ListingAddress :listing="listing" />
                </Link>
            </div>
            <div class="grid grid-cols-2">
                <Link
                    class="border rounded border-black dark:border-black dark:bg-white dark:text-black hover:bg-black hover:text-white"
                    :href="route('listing.edit', { listing: listing.id })"
                    as="button"
                    >Edit</Link
                >
                <Link
                    class="border rounded border-black dark:border-black dark:bg-white dark:text-black hover:bg-black hover:text-white"
                    method="DELETE"
                    :href="route('listing.destroy', { listing: listing.id })"
                    as="button"
                    >Delete</Link
                >
            </div>
            <!-- <div class="grid justify-items-end"></div> -->
        </div>
    </div>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
import ListingAddress from "../../Components/ListingAddress.vue";
defineProps({
    listings: Array,
});
</script>
<script>
import MainLayout from "../../Layouts/MainLayout.vue";
export default {
    layout: MainLayout,
    components: { ListingAddress },
};
</script>
