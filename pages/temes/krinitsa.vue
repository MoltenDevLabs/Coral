<template>
  <div class="relative">
    <div>
      <button
        class="absolute top-0 right-2 z-50"
        @click="themeStore.toggleTheme()"
      >
        <i
          class="material-icons-outlined theme-icon scale-90"
          :class="{ 'border-surface-900': !themeStore.isDarkTheme }"
          :title="themeStore.isDarkTheme ? 'Light mode' : 'Dark mode'"
        >
          {{ themeStore.isDarkTheme ? "light_mode" : "dark_mode" }}
        </i>
      </button>
    </div>
    <div>
      <h3>Krinitsa (nunu)</h3>
      <div>
        <img src="@/assets/images/krinitsa.jpg" alt="" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { useThemeStore } from "~/stores/themeStore";
const themeStore = useThemeStore();
</script>

<style scoped></style>
