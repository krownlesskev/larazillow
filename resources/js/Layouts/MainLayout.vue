<template>
    <Link href="/">Home</Link>&nbsp;
    <Link href="/hello">Show Page</Link>
    <div>Timer for this page: {{ timer }}</div>
    <slot></slot>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
import { ref } from "vue";

const timer = ref(0);
setInterval(() => {
    timer.value++;
}, 1000);
</script>
