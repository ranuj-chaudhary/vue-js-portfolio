# Vue 3 + Vite
Move into your new project directory and install the initial dependencies:

Bash

cd project-name
npm install

2. Install and Configure Tailwind CSS (v4.1)
The installation for Tailwind CSS v4.1 is simpler as it integrates directly with Vite.

2.1 Install Dependencies
Bash

npm install tailwindcss @tailwindcss/vite
2.2 Configure Vite (vite.config.js)
Update your Vite config to include the Tailwind plugin. This replaces the need for separate PostCSS configuration.

JavaScript

import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
import vue from '@vitejs/plugin-vue'

export default defineConfig({
  plugins: [
    vue(),
    tailwindcss(),
  ],
})
2.3 Configure Tailwind (tailwind.config.js)
Create the tailwind.config.js file if it doesn't exist, and configure the content paths:

JavaScript

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
2.4 Import Tailwind Styles
Add the Tailwind directives to your main CSS file (e.g., src/style.css):

CSS

@tailwind base;
@tailwind components;
@tailwind utilities;

3. Install Heroicons for Vue
This project uses Heroicons for clean, scalable SVG icons.

3.1 Install Heroicons
Bash

npm install @heroicons/vue

3.2 Use Heroicons in Components
Icons are imported from the @heroicons/vue/24/outline or /24/solid paths.

Example Usage:

Code snippet

<script setup>
import { UserIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <UserIcon class="w-6 h-6 text-gray-700" />
</template>

4. Install and Configure Vue Router
Implement client-side routing.

4.1 Install Vue Router
Bash

npm install vue-router
4.2 Configure Router (src/router/index.js)
Create the router configuration file:

JavaScript

import { createRouter, createWebHistory } from 'vue-router'

const routes = [] // Define your routes here

const router = createRouter({
  history: createWebHistory(),
  routes,
})

export default router
4.3 Register Router (src/main.js)
Register the router instance in your main application file:

JavaScript

import { createApp } from 'vue'
import App from './App.vue'
import router from './router'

createApp(App).use(router).mount('#app')
▶️ Running the Project
Start the development server with:

Bash

npm run dev
🎯 Project Purpose
This portfolio project is built to achieve the following goals:

Build a professional and highly customizable frontend portfolio.

Practice and solidify skills in the Vue 3 Composition API.

Utilize Tailwind CSS for creating a responsive, utility-first user interface.

Follow a scalable and maintainable frontend project structure.

👨‍💻 Author
Ranuj Chaudhary

Frontend Developer







