<script setup>
import { ref } from "vue";
import { useHead } from "#imports";

useHead({
    title: "Landing - A/B Optimization",
});

const problems = ref([
    "Decisions based on opinions, not data",
    "Wasted marketing budget on ineffective campaigns",
    "Missed opportunities for optimization",
]);

const solutions = ref([
    "Real-time data and actionable insights",
    "Optimized campaigns with higher ROI",
    "Continuous improvement and growth",
]);

const stats = ref([
    { value: "47%", label: "Average Conversion Increase", color: "text-blue-400" },
    { value: "10K+", label: "Active Users", color: "text-green-400" },
    { value: "1M+", label: "Tests Completed", color: "text-purple-400" },
    { value: "99.9%", label: "Uptime Guarantee", color: "text-yellow-400" },
]);

const brandNames = ref(["TechCorp", "GrowthCo", "StartupXYZ", "DataFlow", "OptimizeNow"]);
</script>

<template>
    <div class="space-y-16">
        <!-- Hero Section -->
        <section class="text-center py-20 bg-gradient-to-br from-blue-50 to-indigo-100 rounded-2xl">
            <h1 class="text-5xl md:text-7xl font-bold text-gray-900 mb-6">
                Transform Your Business
                <span class="block text-blue-600">With Smart Testing</span>
            </h1>

            <p class="text-xl text-gray-600 mb-10 max-w-4xl mx-auto leading-relaxed">
                Discover the power of data-driven optimization. Our advanced A/B testing platform helps you make
                informed decisions that drive real growth and maximize conversions.
            </p>

            <ABTestComponent test-id="landing-page-main-cta" />
        </section>

        <!-- Problem & Solution -->
        <section class="py-16">
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <!-- Problems Column -->
                <div>
                    <h2 class="text-3xl font-bold text-gray-900 mb-6">Stop Guessing, Start Growing</h2>
                    <p class="text-gray-600 mb-6 text-lg">
                        Too many businesses make crucial decisions based on assumptions rather than data. This leads to
                        missed opportunities, wasted resources, and stunted growth.
                    </p>

                    <ul class="space-y-4">
                        <li v-for="(item, index) in problems" :key="'p-' + index" class="flex items-start">
                            <div class="bg-red-100 p-1 rounded-full mr-3 mt-1">
                                <svg class="w-4 h-4 text-red-600" fill="currentColor" viewBox="0 0 20 20">
                                    <path
                                        fill-rule="evenodd"
                                        clip-rule="evenodd"
                                        d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 011.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                                    />
                                </svg>
                            </div>
                            <span class="text-gray-700">{{ item }}</span>
                        </li>
                    </ul>
                </div>

                <!-- Solution Column -->
                <div>
                    <h3 class="text-2xl font-bold text-gray-900 mb-6">Our Solution Changes Everything</h3>
                    <p class="text-gray-600 mb-6 text-lg">
                        With our advanced A/B testing platform, every decision becomes data-driven, every campaign gets
                        optimized, and every opportunity gets maximized.
                    </p>

                    <ul class="space-y-4">
                        <li v-for="(item, index) in solutions" :key="'s-' + index" class="flex items-start">
                            <div class="bg-green-100 p-1 rounded-full mr-3 mt-1">
                                <svg class="w-4 h-4 text-green-600" fill="currentColor" viewBox="0 0 20 20">
                                    <path
                                        fill-rule="evenodd"
                                        clip-rule="evenodd"
                                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                                    />
                                </svg>
                            </div>
                            <span class="text-gray-700">{{ item }}</span>
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="py-16 bg-gray-900 text-white rounded-2xl">
            <div class="text-center">
                <h2 class="text-3xl font-bold mb-12">Proven Results Across Industries</h2>

                <div class="grid md:grid-cols-4 gap-8">
                    <div v-for="stat in stats" :key="stat.label">
                        <div :class="`text-4xl font-bold ${stat.color} mb-2`">
                            {{ stat.value }}
                        </div>
                        <div class="text-gray-300">{{ stat.label }}</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Social Proof -->
        <section class="py-16">
            <div class="text-center">
                <h2 class="text-2xl font-semibold text-gray-600 mb-8">Trusted by leading companies worldwide</h2>

                <div class="flex justify-center items-center space-x-12 opacity-60">
                    <div v-for="name in brandNames" :key="name" class="text-2xl font-bold text-gray-400">
                        {{ name }}
                    </div>
                </div>
            </div>
        </section>

        <!-- Final CTA -->
        <section class="py-20 text-center bg-gradient-to-r from-purple-600 to-blue-600 text-white rounded-2xl">
            <h2 class="text-4xl font-bold mb-6">Ready to Double Your Conversions?</h2>

            <p class="text-xl mb-10 opacity-90 max-w-2xl mx-auto">
                Join thousands of smart businesses who've already transformed their growth with data-driven
                optimization.
            </p>

            <div class="mb-8">
                <ABTestComponent test-id="landing-page-bottom-cta" />
            </div>

            <p class="text-sm opacity-75">No credit card required • Setup in 5 minutes • Cancel anytime</p>
        </section>
    </div>
</template>
