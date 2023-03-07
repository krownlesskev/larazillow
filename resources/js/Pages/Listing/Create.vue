<template>
    <form @submit.prevent="form.post(route('listing.store'))">
        <div>
            <div>
                <label>Beds</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model.number="form.beds"
                    type="text"
                />
                <div class="error" v-if="form.errors.beds">
                    {{ form.errors.beds }}
                </div>
            </div>
            <div>
                <label>Baths</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model.number="form.baths"
                    type="text"
                />
                <div class="error" v-if="form.errors.baths">
                    {{ form.errors.baths }}
                </div>
            </div>
            <div>
                <label>Area</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model.number="form.area"
                    type="text"
                />
                <div class="error" v-if="form.errors.area">
                    {{ form.errors.area }}
                </div>
            </div>
            <div>
                <label>City</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model="form.city"
                    type="text"
                    placeholder="City Name"
                />
                <div class="error" v-if="form.errors.city">
                    {{ form.errors.city }}
                </div>
            </div>
            <div>
                <label>Postal Code</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model="form.code"
                    type="text"
                />
                <div class="error" v-if="form.errors.code">
                    {{ form.errors.code }}
                </div>
            </div>
            <div>
                <label>Street #</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model="form.street_nr"
                    type="text"
                />
                <div class="error" v-if="form.errors.street_nr">
                    {{ form.errors.street_nr }}
                </div>
            </div>
            <div>
                <label>Street</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model="form.street"
                    type="text"
                    placeholder="Street Name"
                />
                <div class="error" v-if="form.errors.street">
                    {{ form.errors.street }}
                </div>
            </div>
            <div>
                <label>Price</label>
                <input
                    class="dark:text-black dark:placeholder:text-black"
                    v-model.number="form.price"
                    type="text"
                />
                <div class="error" v-if="form.errors.price">
                    {{ form.errors.price }}
                </div>
            </div>
            <div>
                <button type="submit">Create</button>
            </div>
        </div>
    </form>
</template>

<script setup>
import { useForm } from "@inertiajs/vue3";

const form = useForm({
    beds: 0,
    baths: 0,
    area: 15,
    city: null,
    code: "123 456",
    street_nr: 0,
    street: null,
    price: 0,
});
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

.error {
    color: red;
}
</style>
