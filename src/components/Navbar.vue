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
              isMenuOpen ? 'opacity-0' : 'top-3 opacity-100',
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
    <nav
      class="fixed inset-0 md:relative flex  items-center justify-center bg-[#111827] md:flex md:bg-transparent"
      :class="isMenuOpen ? 'block' : 'hidden'"
    >
      <ul
        class="flex flex-col items-center md:flex-row space-y-5 md:space-y-0 md:space-x-5"
      >
        <li v-for="item in Menu" class="relative">
          <a
            :href="item.href"
            class="relative block text-blue-100 hover:text-blue-400 transition-all duration-300 text-xl md:text-base font-medium group"
            @click="scrollIntoSection(item.href)"
          >
            {{ item.name }}
            <span
              class="absolute left-0 ease-out -translate-x-1 group-hover:translate-x-0 bottom-0 w-0 bg-blue-400 group-hover:w-full h-0.5 transition-all duration-300"
            ></span>
          </a>
        </li>
      </ul>
      <div class="mt-8 md:mt-0 md:ml-8">
        <button class="px-6 py-2 bg-blue-400 text-white rounded-full bg-linear-to-r from-blue-500  to-cyan-500  hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300 cursor-pointer hover:scale-105">
          Lets Talk
        </button>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref, watch } from "vue";
const isMenuOpen = ref(false);
console.log(isMenuOpen.value);
const Menu = ref([
  { name: "Services", href: "#services" },
  { name: "About Me", href: "#about" },
  { name: "Skills", href: "#skills" },
  { name: "Services", href: "#services" },
  { name: "Services", href: "#services" },
]);

const scrollIntoSection = (id) => {
  isMenuOpen.value = false; // Close the menu when a link is clicked
  const section = document.getElementById(id);
  if (section) {
    section.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<style lang="scss" scoped></style>
