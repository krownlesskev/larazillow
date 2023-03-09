<template>
    <div>Home</div>
    <div>
        {{ message }}
    </div>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
defineProps({
    message: String,
});
</script>
