<template>
    <div>
        <!-- Loader -->
        <div v-if="variant === null" class="animate-pulse bg-gray-200 h-12 w-48 rounded-lg mx-auto"></div>

        <!-- Variant content -->
        <div
            v-else
            class="p-6 rounded-lg border-2 mx-auto max-w-md"
            :class="variant === 'A' ? 'variant-a' : 'variant-b'"
        >
            <!-- Variant A -->
            <div v-if="variant === 'A'">
                <h3 class="text-xl font-semibold text-blue-800 mb-3">Start Your Free Trial</h3>
                <p class="text-blue-600 mb-4">Get unlimited access for 30 days. No credit card required.</p>
                <button
                    class="cta-button-a px-6 py-3 rounded-lg font-semibold w-full transition-colors"
                    @click="handleClick"
                >
                    Try Free for 30 Days
                </button>
            </div>

            <!-- Variant B -->
            <div v-else>
                <h3 class="text-xl font-semibold text-green-800 mb-3">Join 10,000+ Happy Users</h3>
                <p class="text-green-600 mb-4">See why businesses trust our platform for their growth.</p>
                <button
                    class="cta-button-b px-6 py-3 rounded-lg font-semibold w-full transition-colors"
                    @click="handleClick"
                >
                    Get Started Today
                </button>
            </div>

            <div class="mt-4 text-xs text-gray-500 text-center">
                Test variant: {{ variant }} | Test ID: {{ testId }}
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

// Props
const props = defineProps({
    testId: {
        type: String,
        required: true,
    },
});

// State
const variant = ref(null); // null | 'A' | 'B'

// Logic
onMounted(() => {
    const key = `ab-test-${props.testId}`;
    const savedVariant = localStorage.getItem(key);

    if (savedVariant === "A" || savedVariant === "B") {
        variant.value = savedVariant;
    } else {
        const newVariant = Math.random() < 0.5 ? "A" : "B";
        variant.value = newVariant;
        localStorage.setItem(key, newVariant);
    }
});

// Methods — now just functions
function handleClick() {
    console.log(`Conversion tracked for variant ${variant.value} on test ${props.testId}`);

    const event = {
        testId: props.testId,
        variant: variant.value,
        timestamp: new Date().toISOString(),
        event: "click",
    };

    console.log("Analytics event:", event);
}
</script>

<style scoped>
.variant-a {
    border-color: #3b82f6;
}

.variant-b {
    border-color: #10b981;
}

.cta-button-a {
    background-color: #3b82f6;
    color: white;
}

.cta-button-b {
    background-color: #10b981;
    color: white;
}
</style>
