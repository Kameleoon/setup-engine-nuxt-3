<script setup>
import { ref } from "vue";
import { useHead } from "#imports";

useHead({
    title: "A/B Testing Platform - Data-Driven Optimization",
    meta: [
        {
            name: "description",
            content: "Experience the power...",
        },
        {
            property: "og:title",
            content: "A/B Testing Platform - Data-Driven Optimization",
        },
        {
            property: "og:description",
            content: "Transform your business with smart A/B testing and optimization",
        },
        { property: "twitter:card", content: "summary_large_image" },
    ],
});

const heroBgStyle = ref({
    backgroundImage:
        "url('https://images.unsplash.com/photo-1551434678-e076c223a692?auto=format&fit=crop&w=2070&q=80')",
    backgroundSize: "cover",
    backgroundPosition: "center",
    backgroundRepeat: "no-repeat",
});
</script>

<template>
    <div class="space-y-12">
        <!-- Hero Section -->
        <section class="relative text-center py-20 min-h-[600px] overflow-hidden rounded-2xl" :style="heroBgStyle">
            <!-- Overlay -->
            <div class="absolute inset-0 bg-gradient-to-br from-blue-50/80 to-purple-50/80 z-0"></div>

            <div class="relative z-10 flex flex-col items-center justify-center h-full">
                <h1 class="text-4xl md:text-6xl font-bold text-gray-900 mb-6">Welcome to Our A/B Testing Platform</h1>

                <p class="text-xl text-gray-600 mb-8 max-w-3xl mx-auto">
                    Experience the power of data-driven decisions with our comprehensive testing platform designed for
                    modern businesses.
                </p>

                <!-- Auto-import works, no import needed -->
                <ABTestComponent test-id="home-hero-cta" />
            </div>
        </section>

        <!-- Features -->
        <section class="py-16 bg-gray-50 rounded-lg">
            <div class="max-w-4xl mx-auto">
                <h2 class="text-3xl font-bold text-center text-gray-900 mb-12">Why Choose Our Platform?</h2>

                <div class="grid md:grid-cols-3 gap-8">
                    <div class="text-center">
                        <div class="bg-blue-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"
                                />
                            </svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900 mb-2">Real-time Analytics</h3>
                        <p class="text-gray-600">
                            Get instant insights into your test performance with live data visualization.
                        </p>
                    </div>

                    <div class="text-center">
                        <div class="bg-green-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M13 10V3L4 14h7v7l9-11h-7z"
                                />
                            </svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900 mb-2">Lightning Fast</h3>
                        <p class="text-gray-600">
                            Deploy tests in minutes and see results immediately with our optimized platform.
                        </p>
                    </div>

                    <div class="text-center">
                        <div class="bg-purple-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
                            <svg class="w-8 h-8 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"
                                />
                            </svg>
                        </div>
                        <h3 class="text-xl font-semibold text-gray-900 mb-2">Enterprise Security</h3>
                        <p class="text-gray-600">
                            Bank-level security ensures your data and tests are always protected.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Testimonials -->
        <TestimonialSection />

        <!-- CTA -->
        <section class="text-center py-16 bg-gradient-to-r from-blue-600 to-purple-600 text-white rounded-lg">
            <h2 class="text-3xl font-bold mb-4">Ready to Start Testing?</h2>
            <p class="text-xl mb-8 opacity-90">Join thousands of businesses optimizing their conversion rates.</p>
            <button
                class="bg-white text-blue-600 px-8 py-3 rounded-lg font-semibold text-lg hover:bg-gray-100 transition-colors"
            >
                Get Started Free
            </button>
        </section>
    </div>
</template>
