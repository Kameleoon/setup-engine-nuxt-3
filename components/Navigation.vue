<template>
    <nav class="bg-white shadow-lg">
        <div class="container mx-auto px-4">
            <div class="flex justify-between items-center py-4">
                <!-- Logo -->
                <NuxtLink to="/" class="text-xl font-bold text-gray-800"> A/B Testing App </NuxtLink>

                <!-- Nav Links -->
                <div class="flex space-x-6">
                    <NuxtLink
                        v-for="link in links"
                        :key="link.href"
                        :to="link.href"
                        class="px-3 py-2 rounded-md text-sm font-medium transition-colors"
                        :class="getLinkClass(link.href)"
                    >
                        {{ link.label }}
                    </NuxtLink>
                </div>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { ref } from "vue";
import { useRoute } from "vue-router";

const route = useRoute();

const links = ref([
    { href: "/", label: "Home" },
    { href: "/landing", label: "Landing" },
    { href: "/pricing", label: "Pricing" },
    { href: "/features", label: "Features" },
]);

function getLinkClass(href) {
    return route.path === href ? "bg-blue-100 text-blue-700" : "text-gray-600 hover:text-gray-800 hover:bg-gray-100";
}
</script>
