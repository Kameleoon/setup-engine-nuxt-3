<script setup>
import { ref } from "vue";
import { useHead } from "#imports";

// SEO (optional)
useHead({
    title: "Features - A/B Testing Platform",
});

/* ---- STATE (migrated from data()) ---- */

const features = ref([
    {
        id: 1,
        title: "Visual Editor",
        description:
            "Create and modify test variants without any coding knowledge. Our drag-and-drop interface makes A/B testing accessible to everyone.",
        icon: "🎨",
        details: ["Point-and-click element editing", "Real-time preview", "No developer required", "WYSIWYG interface"],
    },
    {
        id: 2,
        title: "Real-Time Analytics",
        description:
            "Monitor your test performance with live data updates, statistical significance calculations, and comprehensive reporting.",
        icon: "📊",
        details: [
            "Live performance metrics",
            "Statistical significance tracking",
            "Custom conversion goals",
            "Automated reporting",
        ],
    },
    {
        id: 3,
        title: "Advanced Targeting",
        description:
            "Target specific audience segments based on demographics, behavior, traffic source, and custom attributes.",
        icon: "🎯",
        details: [
            "Geographic targeting",
            "Device & browser targeting",
            "Custom audience segments",
            "Behavioral triggers",
        ],
    },
    {
        id: 4,
        title: "Smart Traffic Distribution",
        description:
            "AI-powered traffic allocation automatically optimizes test distribution for maximum statistical power.",
        icon: "🤖",
        details: [
            "AI-powered optimization",
            "Automatic traffic allocation",
            "Early winner detection",
            "Confidence intervals",
        ],
    },
    {
        id: 5,
        title: "Integration Hub",
        description:
            "Connect seamlessly with your existing tools through our extensive library of integrations and APIs.",
        icon: "🔌",
        details: ["Google Analytics integration", "Marketing automation tools", "CRM connections", "REST API access"],
    },
    {
        id: 6,
        title: "Enterprise Security",
        description:
            "Bank-level security with SOC 2 compliance, data encryption, and privacy controls to protect your business.",
        icon: "🔒",
        details: ["SOC 2 Type II certified", "End-to-end encryption", "GDPR compliant", "Regular security audits"],
    },
]);

const benefits = ref([
    {
        title: "Increase Conversions",
        description: "Optimize every element of your website to maximize conversion rates and revenue.",
        stat: "47% average lift",
        color: "blue",
    },
    {
        title: "Reduce Risk",
        description: "Test changes before full deployment to minimize the risk of negative impact.",
        stat: "95% confidence",
        color: "green",
    },
    {
        title: "Save Time",
        description: "Automated testing and reporting save hours of manual analysis and guesswork.",
        stat: "10x faster insights",
        color: "purple",
    },
    {
        title: "Scale Growth",
        description: "Continuous optimization compound over time to accelerate long-term growth.",
        stat: "2.3x revenue growth",
        color: "orange",
    },
]);

const howItWorks = ref([
    {
        title: "Create Your Test",
        text: "Use our visual editor to create test variants or upload your own designs. Define your success metrics and target audience.",
        bg: "bg-blue-100",
        color: "text-blue-600",
    },
    {
        title: "Launch & Monitor",
        text: "Deploy your test with one click and watch real-time results come in. Our AI monitors statistical significance automatically.",
        bg: "bg-green-100",
        color: "text-green-600",
    },
    {
        title: "Implement Winners",
        text: "Once a winner is detected, implement the changes permanently and start your next optimization project.",
        bg: "bg-purple-100",
        color: "text-purple-600",
    },
]);

const caseStats = ref([
    { value: "73%", label: "Increase in signups" },
    { value: "6 weeks", label: "Time to results" },
    { value: "$2.4M", label: "Additional ARR" },
]);
</script>

<template>
    <div class="space-y-20">
        <!-- Hero Section -->
        <section class="text-center py-16">
            <h1 class="text-4xl md:text-6xl font-bold text-gray-900 mb-6">
                Powerful Features for
                <span class="block text-blue-600">Smarter Testing</span>
            </h1>
            <p class="text-xl text-gray-600 mb-8 max-w-3xl mx-auto">
                Everything you need to run sophisticated A/B tests, analyze results, and optimize your conversion funnel
                with confidence.
            </p>
            <ABTestComponent test-id="features-page-hero" />
        </section>

        <!-- Key Benefits -->
        <section class="py-16">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold text-gray-900 mb-4">Why Choose Our A/B Testing Platform?</h2>
                <p class="text-gray-600 text-lg">Proven results that speak for themselves</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div v-for="(benefit, index) in benefits" :key="index" class="text-center">
                    <div
                        :class="`w-16 h-16 mx-auto mb-6 rounded-full flex items-center justify-center bg-${benefit.color}-100`"
                    >
                        <div :class="`text-2xl font-bold text-${benefit.color}-600`">{{ benefit.stat }}</div>
                    </div>
                    <h3 class="text-xl font-semibold text-gray-900 mb-3">{{ benefit.title }}</h3>
                    <p class="text-gray-600">{{ benefit.description }}</p>
                </div>
            </div>
        </section>

        <!-- Detailed Features -->
        <section class="py-20 bg-gray-50 rounded-2xl">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold text-gray-900 mb-4">Complete Testing Suite</h2>
                <p class="text-gray-600 text-lg max-w-2xl mx-auto">
                    From simple split tests to complex multivariate experiments, our platform has everything you need to
                    optimize your business.
                </p>
            </div>

            <div class="grid lg:grid-cols-2 gap-12">
                <div v-for="feature in features" :key="feature.id" class="bg-white p-8 rounded-xl shadow-sm">
                    <div class="flex items-start mb-6">
                        <div class="text-4xl mr-4">{{ feature.icon }}</div>
                        <div>
                            <h3 class="text-2xl font-bold text-gray-900 mb-3">{{ feature.title }}</h3>
                            <p class="text-gray-600 text-lg">{{ feature.description }}</p>
                        </div>
                    </div>

                    <div class="space-y-3">
                        <div
                            v-for="(detail, detailIndex) in feature.details"
                            :key="detailIndex"
                            class="flex items-center"
                        >
                            <div class="bg-green-100 p-1 rounded-full mr-3">
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
                            <span class="text-gray-700">{{ detail }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- How It Works -->
        <section class="py-16">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold text-gray-900 mb-4">How It Works</h2>
                <p class="text-gray-600 text-lg">Get started with A/B testing in just a few simple steps</p>
            </div>

            <div class="grid md:grid-cols-3 gap-12">
                <div v-for="(step, index) in howItWorks" :key="index" class="text-center">
                    <div :class="`w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-6 ${step.bg}`">
                        <span :class="`text-2xl font-bold ${step.color}`">{{ index + 1 }}</span>
                    </div>
                    <h3 class="text-xl font-semibold text-gray-900 mb-3">{{ step.title }}</h3>
                    <p class="text-gray-600">{{ step.text }}</p>
                </div>
            </div>
        </section>

        <!-- Case Study -->
        <section class="py-20 bg-gradient-to-br from-blue-600 to-purple-700 text-white rounded-2xl">
            <div class="text-center max-w-4xl mx-auto">
                <h2 class="text-3xl font-bold mb-6">Real Results from Real Businesses</h2>

                <div class="bg-white/10 backdrop-blur-sm rounded-xl p-8 mb-8">
                    <blockquote class="text-xl mb-6">
                        "We increased our signup rate by 73% in just 6 weeks using their A/B testing platform. The
                        insights we gained completely changed how we think about our user experience."
                    </blockquote>

                    <div class="flex items-center justify-center">
                        <div class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center mr-4">
                            <span class="font-bold">JD</span>
                        </div>
                        <div>
                            <div class="font-semibold">Jessica Davis</div>
                            <div class="opacity-80">VP of Growth, TechStartup Inc.</div>
                        </div>
                    </div>
                </div>

                <div class="grid md:grid-cols-3 gap-6 text-center">
                    <div v-for="stat in caseStats" :key="stat.label">
                        <div class="text-3xl font-bold mb-2">{{ stat.value }}</div>
                        <div class="opacity-80">{{ stat.label }}</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Final CTA -->
        <section class="py-16 text-center">
            <h2 class="text-3xl font-bold text-gray-900 mb-6">Ready to Start Optimizing?</h2>
            <p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
                Join thousands of businesses who've transformed their growth with data-driven A/B testing.
            </p>

            <ABTestComponent test-id="features-page-bottom-cta" />

            <div class="mt-8 text-sm text-gray-500">
                ✓ 14-day free trial &nbsp; • &nbsp; ✓ No credit card required &nbsp; • &nbsp; ✓ Setup in 5 minutes
            </div>
        </section>
    </div>
</template>
