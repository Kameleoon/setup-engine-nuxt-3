<script setup>
import KameleoonHead from "~/integrations/Kameleoon/components/KameleoonHead.vue";
import KameleoonScriptLoader from "~/integrations/Kameleoon/components/KameleoonScriptLoader.client.vue";
</script>

<template>
    <!-- SSR: preload + anti-flicker -->
    <KameleoonHead />

    <!-- Client: load script after hydration -->
    <KameleoonScriptLoader />

    <!-- Layout UI -->
    <div class="min-h-screen bg-background font-inter">
        <Navigation />

        <main class="container mx-auto px-4 py-8">
            <NuxtPage />
        </main>
    </div>
</template>
