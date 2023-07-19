<template>
  <header class="fixed left-0 right-0 top-0 h-14 z-20 bg-light-secondary dark:bg-dark-secondary">
    <nav class="flex items-center justify-around w-full h-full">
      <RouterLink class="hover:text-blue-700" to="/">{{ t("pages.home") }}</RouterLink>
      <RouterLink class="hover:text-blue-700" to="/about">{{ t("pages.about") }}</RouterLink>
      <div class="space-x-2">
        <label>{{ t("language") }}</label>
        <select v-model="i18n.global.locale" class="text-black">
          <option value="ru-RU">ru</option>
          <option value="en-US">en</option>
        </select>
      </div>
      <div @click="isDark = !isDark">{{ isDark ? t("dark") : t("light") }}</div>
    </nav>
  </header>
  <main class="mt-14">
    <RouterView />
  </main>
</template>

<script lang="ts" setup>
import { useDark } from "@vueuse/core";

const isDark = useDark({ attribute: "class" });
</script>
