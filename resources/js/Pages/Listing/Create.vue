<template>
    <form action="">
        <div>
            <div>
                <label>Beds</label>
                <input type="text" />
            </div>
            <div>
                <label>Baths</label>
                <input type="text" />
            </div>
            <div>
                <label>Area</label>
                <input type="text" />
            </div>
            <div>
                <label>City</label>
                <input type="text" />
            </div>
            <div>
                <label>Postal Code</label>
                <input type="text" />
            </div>
            <div>
                <label>Street #</label>
                <input type="text" />
            </div>
            <div>
                <label>Street</label>
                <input type="text" />
            </div>
            <div>
                <label>Price</label>
                <input type="text" />
            </div>
            <div>
                <button type="submit">Create</button>
            </div>
        </div>
    </form>
</template>

<script setup>
import { Link } from "@inertiajs/vue3";
</script>
<script>
import MainLayout from "../../Layouts/MainLayout.vue";
export default {
    layout: MainLayout,
};
</script>

<style scope>
label {
    margin-right: 2em;
}

div {
    padding: 2px;
}
</style>
