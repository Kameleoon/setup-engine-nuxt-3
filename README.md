# Kameleoon Integration for Nuxt 3

A clean, SSR-safe and hydration-friendly way to load the Kameleoon engine inside a Nuxt 3 project — without flicker and without hydration mismatch errors.

---

## Architecture Overview

The integration consists of **two Vue components**, each responsible for a specific phase of the Nuxt lifecycle:

| Component                          | Runs                              | Purpose                                                                |
| ---------------------------------- | --------------------------------- | ---------------------------------------------------------------------- |
| `KameleoonHead.vue`                | **SSR only**                      | Injects preload tag + anti-flicker CSS into `<head>` before hydration  |
| `KameleoonScriptLoader.client.vue` | **Client only (after hydration)** | Loads the engine script, removes flicker CSS, applies timeout fallback |

This separation ensures **fast loading + zero hydration warnings**.

---

## Folder Structure

```
integrations/
└── Kameleoon/
    ├── components/
    │   ├── KameleoonHead.vue
    │   └── KameleoonScriptLoader.client.vue
    └── sitecode.ts
```

---

## Installation & Usage

1. Copy the folder into your project: `integrations/Kameleoon`

2. Import both components inside your layout (recommended: `layouts/default.vue`):

```vue
<script setup>
import KameleoonHead from "~/integrations/Kameleoon/components/KameleoonHead.vue";
import KameleoonScriptLoader from "~/integrations/Kameleoon/components/KameleoonScriptLoader.client.vue";
</script>

<template>
    <!-- SSR: preload + anti-flicker -->
    <KameleoonHead />

    <!-- Client: load script after hydration -->
    <KameleoonScriptLoader />

    <div class="min-h-screen">
        <NuxtPage />
    </div>
</template>
```

3. Configure your Sitecode once in:

```
integrations/Kameleoon/sitecode.ts
```

Example:

```ts
export const SITECODE_SRC = "https://SITECODE.kameleoon.io/engine.js";
```

---

## 🚀 How It Works (Timeline)

| Phase                  | What Happens                                         | Component                          |
| ---------------------- | ---------------------------------------------------- | ---------------------------------- |
| **SSR Rendering**      | Preload link + anti-flicker CSS inserted into head   | `KameleoonHead.vue`                |
| **Client Hydration**   | Vue hydrates the DOM — no mismatches occur           | —                                  |
| **Post Hydration**     | Script loads asynchronously, Kameleoon initializes   | `KameleoonScriptLoader.client.vue` |
| **Fallback Safe-Exit** | CSS removed automatically if script fails or is slow | `KameleoonScriptLoader.client.vue` |

---

## Behavior Guarantees

-   ✔ No hydration mismatch warnings in console
-   ✔ No UI flickering before Kameleoon loads
-   ✔ Script loads **only once** (even after SPA navigation)
-   ✔ Works with layouts, pages, and conditional rendering
