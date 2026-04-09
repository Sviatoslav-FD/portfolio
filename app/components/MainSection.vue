<template>
  <main
    id="main-section"
    class="flex flex-col gap-4 items-center min-h-full md:p-16 p-4 bg-[url(/images/hero.png)] bg-cover bg-center"
    role="main"
    aria-labelledby="main-section-title"
  >
    <AppBadge class="font-thin md:text-2xl text-md md:w-auto w-full">
      Senior Frontend/Full-stack Developer
    </AppBadge>

    <h1
      id="main-section-title"
      class="md:text-7xl text-4xl font-thin"
    >
      Sviatoslav Panevnyk
    </h1>

    <p class="bg-black/50 p-4 rounded-lg border border-green-500">
      Building modern web applications with cutting-edge technologies and a passion for creating seamless user experiences.
      With expertise in JavaScript, TypeScript, Vue, React, and Node.js, I specialize in crafting scalable and efficient solutions that drive business success.
      Explore my portfolio to see how I bring ideas to life through innovative software development.
    </p>

    <AppBadge class="font-thin md:w-auto w-full">
      <div class="flex md:items-center justify-between gap-8 md:h-auto h-6">
        <p class="flex items-center">
          <IconJavascript class="mr-1" />
          <span class="md:block hidden">Javascript</span>
        </p>
        <p class="flex items-center">
          <IconTypescript class="mr-1" />
          <span class="md:block hidden">TypeScript</span>
        </p>
        <p class="flex items-center">
          <IconVue class="mr-1" />
          <span class="md:block hidden">Vue</span>
        </p>
        <p class="flex items-center">
          <IconReact class="mr-1" />
          <span class="md:block hidden">React</span>
        </p>
        <p class="flex items-center">
          <IconNode class="mr-1" />
          <span class="md:block hidden">Node.js</span>
        </p>
      </div>
    </AppBadge>

    <ul class="flex justify-between gap-2">
      <li 
        v-for="(value, key) in items"
        :key
        class="bg-black/50 md:py-4 md:px-8 p-2 rounded-lg border border-green-500"
      >
        <p class="text-xl font-semibold text-green-500">{{ key }}</p>
        <p class="font-thin">{{ value }}</p>
      </li>
    </ul>

    <AppButton class="w-fit flex items-center">
      <IconForm class="mr-2" />
      Get In Touch
    </AppButton>
  </main>
</template>

<script lang="ts" setup>
import AppBadge from '@/components/shared/AppBadge.vue'
import AppButton from '@/components/shared/AppButton.vue'
import IconJavascript from '@/components/icons/IconJavascript.vue'
import IconTypescript from '@/components/icons/IconTypescript.vue'
import IconVue from '@/components/icons/IconVue.vue'
import IconReact from '@/components/icons/IconReact.vue'
import IconNode from '@/components/icons/IconNode.vue'
import IconForm from './icons/IconForm.vue'

const items = {
  "8+": "Years of Experience",
  "20+": "Technologies Used",
  "50+": "Projects Completed",
}
</script>
