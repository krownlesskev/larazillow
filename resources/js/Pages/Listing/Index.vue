<template>
    <div v-for="(listing, index) in listings" :key="listing.id">
        <div>
            <Link :href="route('listing.show', { listing: listing.id })">
                <ListingAddress :listing="listing" />
            </Link>
        </div>
        <div>
            <Link
                :href="route('listing.edit', { listing: listing.id })"
                as="button"
                >Edit</Link
            >
        </div>
        <div>
            <Link
                method="DELETE"
                :href="route('listing.destroy', { listing: listing.id })"
                as="button"
                >Delete</Link
            >
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
