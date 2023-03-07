<template>
    <Link href="/">Home </Link>
    <!-- <Link href="/hello">Show Page </Link> -->
    <Link href="/listing">Listings </Link>
    <Link href="/listing/create">Create Listing </Link>
    <!-- <div>Timer for this page: {{ timer }}</div> -->
    <div v-if="flash.success" class="success">
        {{ flash.success }}
    </div>
    <slot></slot>
</template>

<script setup>
import { computed } from "vue";
import { Link, usePage } from "@inertiajs/vue3";
import { ref } from "vue";

defineProps({
    flash: Object,
});

// const page = usePage();
// const flashSuccess = computed(() => page.props.flash.success);
// const timer = ref(0);
// setInterval(() => {
//     timer.value++;
// }, 1000);
</script>

<style scoped>
.success {
    background-color: green;
    color: white;
}
</style>
