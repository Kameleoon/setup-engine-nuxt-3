<script setup>
defineOptions({ name: "KameleoonScriptLoader" });

import { nextTick, onMounted } from "vue";
import { SITECODE_SRC } from "~/integrations/Kameleoon/sitecode";

onMounted(async () => {
    await nextTick();

    const kameleoonLoadingTimeout = 500;

    window.kameleoonQueue = window.kameleoonQueue || [];
    window.kameleoonStartLoadTime = Date.now();

    window.kameleoonDisplayPage = function (fromEngine) {
        if (!fromEngine) {
            window.kameleoonTimeout = true;
        }
        document.getElementById("kameleoonLoadingStyleSheet")?.remove();
    };

    window.kameleoonDisplayPageTimeOut = setTimeout(window.kameleoonDisplayPage, kameleoonLoadingTimeout);

    const alreadyLoaded = document.querySelector(`script[src*="${SITECODE_SRC}"]`);
    if (!alreadyLoaded) {
        const script = document.createElement("script");
        script.src = SITECODE_SRC;
        script.async = true;
        document.head.appendChild(script);
    }
});
</script>

<template>
    <!-- nothing rendered -->
</template>
