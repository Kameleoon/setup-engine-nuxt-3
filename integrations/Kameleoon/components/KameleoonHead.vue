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
                children: "* { visibility:hidden!important; background-image:none!important; }",
            },
        ],
    });
}
</script>

<template>
    <!-- intentionally empty to avoid hydration mismatches -->
</template>
