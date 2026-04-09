<template>
  <main
    id="main-section"
    class="p-4 flex gap-8 min-h-screen items-center"
    role="region"
    aria-labelledby="main-section-title">
    <div class="w-1/2 flex flex-col justify-between gap-8">
      <AppBadge>
        Senior Frontend/Full-stack Developer
      </AppBadge>

      <AppBadge>
        <div class="flex items-center justify-center gap-8">
          <p class="flex items-center">
            <IconJavascript class="mr-1" />Javascript
          </p>
          <p class="flex items-center">
            <IconTypescript class="mr-1" />TypeScript
          </p>
          <p class="flex items-center">
            <IconVue class="mr-1" />Vue
          </p>
          <p class="flex items-center">
            <IconReact class="mr-1" />React
          </p>
          <p class="flex items-center">
            <IconNode class="mr-1" />Node.js
          </p>
        </div>
      </AppBadge>

      <h1 id="main-section-title" class="text-7xl font-thin">Software Engineer Portfolio</h1>

      <p class="text-white/70">
        Building modern web applications with cutting-edge technologies and a passion for creating seamless user experiences.
        With expertise in JavaScript, TypeScript, Vue, React, and Node.js, I specialize in crafting scalable and efficient solutions that drive business success.
        Explore my portfolio to see how I bring ideas to life through innovative software development.
      </p>

      <ul class="flex justify-between gap-2">
        <li v-for="(value, key) in items" :key="key">
          <p class="text-xl font-semibold text-green-500">{{ key }}</p>
          <p class="font-thin text-sm">{{ value }}</p>
        </li>
      </ul>

      <AppButton class="w-fit flex items-center">
        <IconForm class="mr-2" />
        Get In Touch
      </AppButton>
    </div>

    <NuxtImg
      src="/images/hero.png"
      alt="hero-image"
      class="w-1/2 bg-green-100 rounded-lg aspect-square text-center"
    />
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
