<template>
    <form @submit.prevent="register">
        <div class="w-1/2 mx-auto">
            <div>
                <label for="name" class="label">Your Name</label>
                <input
                    type="text"
                    id="name"
                    class="input"
                    v-model="form.name"
                    autocomplete="name"
                />
                <div class="input-error" v-if="form.errors.name">
                    {{ form.errors.name }}
                </div>
            </div>
            <div class="mt-4">
                <label for="email" class="label">Email</label>
                <input
                    type="text"
                    id="email"
                    class="input"
                    v-model="form.email"
                    autocomplete="email"
                />
                <div class="input-error" v-if="form.errors.email">
                    {{ form.errors.email }}
                </div>
            </div>
            <div class="mt-4">
                <label for="password" class="label">Password</label>
                <input
                    type="password"
                    id="password"
                    class="input"
                    v-model="form.password"
                    autocomplete="current-password"
                />
                <div class="input-error" v-if="form.errors.password">
                    {{ form.errors.password }}
                </div>
            </div>
            <div class="mt-4">
                <label for="password_confirmation" class="label"
                    >Confirm Password</label
                >
                <input
                    type="password"
                    id="password_confirmation"
                    class="input"
                    v-model="form.password_confirmation"
                    autocomplete="current-password"
                />
            </div>
            <div class="mt-8">
                <button class="btn-primary w-full" type="submit">
                    Create Account
                </button>
                <div class="mt-2 text-center w-full">
                    <Link class="w-full" :href="route('login')"
                        >Have an account? Click here.</Link
                    >
                </div>
            </div>
        </div>
    </form>
</template>

<script setup>
import { useForm, Link } from "@inertiajs/vue3";

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null,
});

const register = () => form.post(route("user-account.store"));
</script>
