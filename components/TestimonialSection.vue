<template>
    <section class="py-16">
        <div class="max-w-6xl mx-auto">
            <h2 class="text-3xl font-bold text-center text-gray-900 mb-12">What Our Customers Say</h2>

            <div class="grid md:grid-cols-3 gap-8">
                <div
                    v-for="testimonial in testimonials"
                    :key="testimonial.id"
                    class="bg-white p-6 rounded-lg shadow-lg border"
                >
                    <div class="flex items-center mb-4">
                        <div
                            class="w-12 h-12 bg-blue-500 text-white rounded-full flex items-center justify-center font-semibold mr-4"
                        >
                            {{ testimonial.avatar }}
                        </div>

                        <div>
                            <h4 class="font-semibold text-gray-900">
                                {{ testimonial.name }}
                            </h4>
                            <p class="text-sm text-gray-600">{{ testimonial.role }} at {{ testimonial.company }}</p>
                        </div>
                    </div>

                    <p class="text-gray-700 italic">"{{ testimonial.content }}"</p>

                    <!-- Stars -->
                    <div class="flex mt-4">
                        <svg
                            v-for="i in 5"
                            :key="i"
                            class="w-5 h-5 text-yellow-400"
                            fill="currentColor"
                            viewBox="0 0 20 20"
                        >
                            <path
                                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
                            />
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from "vue";

const testimonials = ref([
    {
        id: 1,
        name: "Sarah Johnson",
        role: "Marketing Director",
        company: "TechCorp",
        content:
            "This A/B testing platform increased our conversion rates by 35% in just 3 months. The insights are incredible!",
        avatar: "SJ",
    },
    {
        id: 2,
        name: "Michael Chen",
        role: "Product Manager",
        company: "GrowthCo",
        content:
            "The real-time analytics and easy setup make this the best testing platform we've used. Highly recommend!",
        avatar: "MC",
    },
    {
        id: 3,
        name: "Emma Williams",
        role: "CEO",
        company: "StartupXYZ",
        content: "Game-changer for our business. We can now make data-driven decisions with confidence.",
        avatar: "EW",
    },
]);
</script>
