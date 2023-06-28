<script lang="ts" setup>
const navLinks = ref<{
    to: string;
    label: string;
}[]
>([
    {
        to: '/pricing',
        label: 'Pricing',
    },
    {
        to: 'https://github.com/aayu5hgit/snippy',
        label: 'GitHub',
    },
    {
        to: '/auth',
        label: 'Login',
    },
])
</script>

<template>
    <div class="fixed top-0 left-0 right-0 border-b border-white/20 bg-white/10 backdrop-filter backdrop-blur-lg z-50">
        <nav class="container py-3 flex justify-between">
            <NuxtLink :to="{name: 'index',}" class="text-2xl font-bold text-white">Snippy URL</NuxtLink>
            <ul class="flex items-center gap-4">
                <li v-for="link in navLinks" :key="link.to">
                    <NuxtLink :to="link.to">{{ link.label }}</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/auth" class="btn">Sign In</NuxtLink>
                </li>
            </ul>
        </nav>
    </div>
</template>

<style>
</style>