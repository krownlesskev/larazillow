<template>
    <Link href="/">Home </Link>
    <Link href="/hello">Show Page </Link>
    <Link href="/listing">Listings </Link>
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

<style>
body {
    background-color: #202124;
    color: #fff;
}
</style>
