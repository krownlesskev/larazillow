<template>
    <form @submit.prevent="form.post(route('listing.store'))">
        <div>
            <div>
                <label>Beds</label>
                <input v-model.number="form.beds" type="text" />
                <div class="error" v-if="form.errors.beds">
                    {{ form.errors.beds }}
                </div>
            </div>
            <div>
                <label>Baths</label>
                <input v-model.number="form.baths" type="text" />
                <div class="error" v-if="form.errors.baths">
                    {{ form.errors.baths }}
                </div>
            </div>
            <div>
                <label>Area</label>
                <input v-model.number="form.area" type="text" />
                <div class="error" v-if="form.errors.area">
                    {{ form.errors.area }}
                </div>
            </div>
            <div>
                <label>City</label>
                <input
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
                <input v-model="form.code" type="text" />
                <div class="error" v-if="form.errors.code">
                    {{ form.errors.code }}
                </div>
            </div>
            <div>
                <label>Street #</label>
                <input v-model="form.street_nr" type="text" />
                <div class="error" v-if="form.errors.street_nr">
                    {{ form.errors.street_nr }}
                </div>
            </div>
            <div>
                <label>Street</label>
                <input
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
                <input v-model.number="form.price" type="text" />
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
    beds: null,
    baths: null,
    area: null,
    city: null,
    code: null,
    street_nr: null,
    street: null,
    price: null,
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
