<template>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 m-4">
        <div
            class="hover:scale-105 ease-in-out duration-500"
            v-for="(listing, index) in listings"
            :key="listing.id"
        >
            <div>
                <Link :href="route('listing.show', { listing: listing.id })">
                    <ListingAddress :listing="listing" />
                </Link>
            </div>
            <div class="grid grid-cols-2 space-x-4 mt-4">
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
