<template>
    <form @submit.prevent="login">
        <div class="w-1/2 mx-auto">
            <div>
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
            <div class="mt-8">
                <button class="btn-primary w-full" type="submit">Login</button>
                <div class="mt-2 text-center w-full">
                    <Link class="w-full" :href="route('user-account.create')"
                        >Need an account? Click here.</Link
                    >
                </div>
            </div>
        </div>
    </form>
</template>

<script setup>
import { useForm, Link } from "@inertiajs/vue3";

const form = useForm({
    email: null,
    password: null,
});

const login = () => form.post(route("login.store"));
</script>
