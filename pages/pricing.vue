<script setup>
import { ref } from "vue";
import { useHead } from "#imports";

useHead({
    title: "Pricing - Choose Your Plan",
});

const plans = ref([
    {
        id: "starter",
        name: "Starter",
        price: "$29",
        period: "per month",
        description: "Perfect for small businesses getting started with A/B testing",
        features: [
            "Up to 5 active tests",
            "10,000 monthly visitors",
            "Basic analytics dashboard",
            "Email support",
            "14-day free trial",
        ],
        popular: false,
        buttonText: "Start Free Trial",
    },
    {
        id: "professional",
        name: "Professional",
        price: "$89",
        period: "per month",
        description: "Ideal for growing businesses with advanced testing needs",
        features: [
            "Unlimited active tests",
            "100,000 monthly visitors",
            "Advanced analytics & reporting",
            "Priority support",
            "Custom integrations",
            "Team collaboration tools",
            "API access",
        ],
        popular: true,
        buttonText: "Start Free Trial",
    },
    {
        id: "enterprise",
        name: "Enterprise",
        price: "Custom",
        period: "pricing",
        description: "For large organizations with complex requirements",
        features: [
            "Unlimited everything",
            "White-label solution",
            "Dedicated account manager",
            "24/7 phone support",
            "Advanced security features",
            "Custom training & onboarding",
            "SLA guarantee",
        ],
        popular: false,
        buttonText: "Contact Sales",
    },
]);

const faqs = ref([
    {
        question: "Can I change plans at any time?",
        answer: "Yes! You can upgrade or downgrade at any time. Changes apply immediately and billing is prorated.",
    },
    {
        question: "What happens if I exceed my visitor limit?",
        answer: "You'll receive a notification. You may upgrade or purchase additional quota — tests continue running.",
    },
    {
        question: "Do you offer annual billing discounts?",
        answer: "Yes, save 20% when choosing annual billing.",
    },
    {
        question: "Is there a free trial?",
        answer: "Absolutely — 14-day free trial, no card required, cancel anytime.",
    },
]);
</script>

<template>
    <div class="space-y-16">
        <!-- Hero Section -->
        <section class="text-center py-16">
            <h1 class="text-4xl md:text-6xl font-bold text-gray-900 mb-6">Simple, Transparent Pricing</h1>

            <p class="text-xl text-gray-600 mb-8 max-w-3xl mx-auto">
                Choose the perfect plan for your business. All plans include our core features and 24/7 support to help
                you succeed.
            </p>

            <div class="flex justify-center mb-12">
                <ABTestComponent test-id="pricing-page-hero" />
            </div>
        </section>

        <!-- Pricing Cards -->
        <section class="py-16">
            <div class="grid lg:grid-cols-3 gap-8 max-w-7xl mx-auto">
                <div
                    v-for="plan in plans"
                    :key="plan.id"
                    class="relative bg-white rounded-2xl shadow-lg border-2 p-8 transition-all duration-300"
                    :class="
                        plan.popular ? 'border-blue-500 transform scale-105' : 'border-gray-200 hover:border-gray-300'
                    "
                >
                    <!-- Badge -->
                    <div v-if="plan.popular" class="absolute -top-4 left-1/2 transform -translate-x-1/2">
                        <span class="bg-blue-500 text-white px-4 py-1 rounded-full text-sm font-medium">
                            Most Popular
                        </span>
                    </div>

                    <!-- Header -->
                    <div class="text-center mb-8">
                        <h3 class="text-2xl font-bold text-gray-900 mb-2">
                            {{ plan.name }}
                        </h3>
                        <p class="text-gray-600 mb-6">{{ plan.description }}</p>

                        <div class="mb-6">
                            <span class="text-5xl font-bold text-gray-900">{{ plan.price }}</span>
                            <span class="text-gray-600 ml-2">{{ plan.period }}</span>
                        </div>
                    </div>

                    <!-- Feature List -->
                    <div class="space-y-4 mb-8">
                        <div v-for="(feature, index) in plan.features" :key="index" class="flex items-start">
                            <div class="bg-green-100 p-1 rounded-full mr-3 mt-0.5 flex-shrink-0">
                                <svg class="w-3 h-3 text-green-600" fill="currentColor" viewBox="0 0 20 20">
                                    <path
                                        fill-rule="evenodd"
                                        clip-rule="evenodd"
                                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 
                      1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 
                      12.586l7.293-7.293a1 1 0 011.414 0z"
                                    />
                                </svg>
                            </div>
                            <span class="text-gray-700">{{ feature }}</span>
                        </div>
                    </div>

                    <!-- CTA -->
                    <button
                        class="w-full py-3 px-6 rounded-lg font-semibold text-lg transition-colors"
                        :class="
                            plan.popular
                                ? 'bg-blue-600 text-white hover:bg-blue-700'
                                : 'bg-gray-100 text-gray-900 hover:bg-gray-200'
                        "
                    >
                        {{ plan.buttonText }}
                    </button>
                </div>
            </div>
        </section>

        <!-- FAQ Section -->
        <section class="py-16 bg-gray-50 rounded-2xl">
            <div class="max-w-4xl mx-auto">
                <h2 class="text-3xl font-bold text-center text-gray-900 mb-12">Frequently Asked Questions</h2>

                <div class="space-y-8">
                    <div v-for="(faq, index) in faqs" :key="index" class="bg-white p-6 rounded-lg shadow-sm">
                        <h3 class="text-xl font-semibold text-gray-900 mb-3">
                            {{ faq.question }}
                        </h3>
                        <p class="text-gray-600">{{ faq.answer }}</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Money Back Guarantee -->
        <section class="py-16 text-center">
            <div class="bg-green-50 rounded-2xl p-12 max-w-4xl mx-auto">
                <div class="flex justify-center mb-6">
                    <div class="bg-green-100 p-4 rounded-full">
                        <svg class="w-12 h-12 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M9 12l2 2 4-4m6 2a9 9 0 
                11-18 0 9 9 0 0118 0z"
                            />
                        </svg>
                    </div>
                </div>

                <h2 class="text-3xl font-bold text-gray-900 mb-4">30-Day Money Back Guarantee</h2>

                <p class="text-xl text-gray-600 mb-8">
                    We're confident you'll love our platform. If you're not completely satisfied within the first 30
                    days, we'll refund every penny. No questions asked.
                </p>

                <ABTestComponent test-id="pricing-guarantee-cta" />
            </div>
        </section>
    </div>
</template>
