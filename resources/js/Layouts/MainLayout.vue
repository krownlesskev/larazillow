<template>
    <Link :href="route('listing.index')">Listings </Link>
    <Link :href="route('listing.create')">Create Listing </Link>
    <div v-if="flash.success" class="success">
        {{ flash.success }}
    </div>
    <slot></slot>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";

defineProps({
    flash: Object,
});
</script>

<style scoped>
.success {
    background-color: green;
    color: white;
}
</style>
