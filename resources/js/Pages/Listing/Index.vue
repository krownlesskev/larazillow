<template>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 m-4">
        <Box v-for="(listing, index) in listings" :key="listing.id">
            <div>
                <Link :href="route('listing.show', { listing: listing.id })">
                    <div class="flex items-center">
                        <Price class="text-2xl" :price="listing.price" />
                    </div>
                    <ListingAddress :listing="listing" />
                </Link>
            </div>
            <div class="grid grid-cols-2 space-x-4 mt-4">
                <Link
                    class="button"
                    :href="route('listing.edit', { listing: listing.id })"
                    as="button"
                    >Edit</Link
                >
                <Link
                    class="button"
                    method="DELETE"
                    :href="route('listing.destroy', { listing: listing.id })"
                    as="button"
                    >Delete</Link
                >
            </div>
            <!-- <div class="grid justify-items-end"></div> -->
        </Box>
    </div>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
import ListingAddress from "@/Components/ListingAddress.vue";
import Price from "@/Components/UI/Price.vue";
import Box from "@/Components/UI/Box.vue";
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
