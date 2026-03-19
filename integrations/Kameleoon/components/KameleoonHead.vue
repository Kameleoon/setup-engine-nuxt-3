<script setup>
defineOptions({ name: "KameleoonHead" });

import { useServerHead } from "#app";
import { SITECODE_SRC } from "../sitecode";

if (process.server) {
    useServerHead({
        link: [
            {
                rel: "preload",
                href: SITECODE_SRC,
                as: "script",
                fetchpriority: "high",
            },
        ],
        style: [
            {
                id: "kameleoonLoadingStyleSheet",
                children:
                    "html::after { content: ''; position: fixed; inset: 0; background: #fff; z-index: 2147483647; }",
            },
        ],
    });
}
</script>

<template>
    <!-- intentionally empty to avoid hydration mismatches -->
</template>
