<template>
  <header
    class="flex justify-between items-center p-6 bg-opacity-50 relative z-20"
  >
    <div
      class="text-3xl font-bold bg-linear-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent"
    >
      Dev <span class="font-black">Portfolio</span>
    </div>
    <div class="z-30 md:hidden">
      <button
        @click="isMenuOpen = !isMenuOpen"
        class="block focus:outline-none p-2 transform rounded-lg bg-blue-800/50 hover:bg-blue-700/50 transition-all duration-300 cursor-pointer"
      >
        <div class="relative h-6 w-6">
          <span
            :class="[
              'absolute left-0 w-6 h-0.5 bg-blue-200',
              isMenuOpen ? 'rotate-45 top-3' : 'top-1',
            ]"
          ></span>
          <span
            :class="[
              'absolute left-0 w-6 h-0.5 bg-blue-200',
              isMenuOpen ? 'opacity-0 ' : 'top-3 opacity-100',
            ]"
          ></span>
          <span
            :class="[
              'absolute left-0 w-6 h-0.5 bg-blue-200',
              isMenuOpen ? '-rotate-45 top-3' : 'top-5',
            ]"
          ></span>
        </div>
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref, watch } from "vue";
const isMenuOpen = ref(false);
watch(isMenuOpen, (newVal, oldVal) => {
  console.log("Count changed:", oldVal, "→", newVal);
});
</script>

<style lang="scss" scoped></style>
