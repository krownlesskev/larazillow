<template>
    <div class="flex flex-col-reverse md:grid md:grid-cols-12 gap-4 m-4">
        <div
            class="col-span-12 md:col-span-7 border border-black dark:border-white flex items-center w-full"
        >
            <span class="w-full text-center font-medium text-gray-500">
                No Images
            </span>
        </div>
        <div class="md:col-span-5 flex flex-col gap-4">
            <ListingAddress :listing="listing" />
            <Box>
                <template #header> Monthly Payments </template>
                <div>
                    <label class="label"
                        >Interest Rate ({{ interestRate }} %)</label
                    >
                    <input
                        class="w-full h-4 bg-gray-200 rounded-lg appearance-none cursor-pointer dark:bg-gray-700"
                        type="range"
                        min="0.1"
                        max="30"
                        step="0.1"
                        v-model.integer="interestRate"
                    />
                    <label class="label"
                        >Duration Rate ({{ duration }} years)</label
                    >
                    <input
                        class="w-full h-4 bg-gray-200 rounded-lg appearance-none cursor-pointer dark:bg-gray-700"
                        type="range"
                        min="3"
                        max="35"
                        step="1"
                        v-model.integer="duration"
                    />

                    <div class="text-gray-600 dark:text-gray-300 mt-2">
                        <div class="text-gray-400">Your monthly payments</div>
                        <Price :price="monthlyPayments" class="text-3xl" />
                    </div>
                </div>
            </Box>
        </div>
    </div>
</template>

<script setup>
import ListingAddress from "@/Components/ListingAddress.vue";
import Box from "@/Components/UI/Box.vue";
import Price from "@/Components/UI/Price.vue";
import { ref, computed } from "vue";

const interestRate = ref(2.5);
const duration = ref(25);

const props = defineProps({
    listing: Object,
});

const monthlyPayments = computed(() => {
    const principle = props.listing.price;
    const monthlyInterest = interestRate.value / 100 / 12;
    const numberOfPaymentMonths = duration.value * 12;

    return (
        (principle *
            monthlyInterest *
            Math.pow(1 + monthlyInterest, numberOfPaymentMonths)) /
        (Math.pow(1 + monthlyInterest, numberOfPaymentMonths) - 1)
    );
});
</script>

<script>
import MainLayout from "../../Layouts/MainLayout.vue";

export default {
    layout: MainLayout,
};
</script>
