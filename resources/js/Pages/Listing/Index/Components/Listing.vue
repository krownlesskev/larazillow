<template>
    <Box>
        <div>
            <Link :href="route('listing.show', { listing: listing.id })">
                <div class="flex items-center gap-1">
                    <Price class="text-2xl" :price="listing.price" />
                    <div class="text-xs text-gray-500">
                        <Price :price="monthlyPayment" /> pm
                    </div>
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
    </Box>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
import ListingAddress from "@/Components/ListingAddress.vue";
import Price from "@/Components/UI/Price.vue";
import Box from "@/Components/UI/Box.vue";

import { useMonthlyPayment } from "@/Composables/useMonthlyPayment";

const props = defineProps({
    listing: Object,
});

const { monthlyPayment } = useMonthlyPayment(props.listing.price, 2.5, 25);
</script>
