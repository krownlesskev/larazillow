<template>
    <Link href="/listing">Listings </Link>
    <Link href="/listing/create">Create Listing </Link>
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
