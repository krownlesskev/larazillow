<template>
    <Link href="/">Home</Link>&nbsp;
    <Link href="/hello">Show Page</Link>
    <slot></slot>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
// defineProps({
//     message: String,
// });
</script>
