<template>
  <AppHeader />
  <h1 class="text-7xl font-thin text-center">Blog</h1>

  <ul class="m-8">
    <li
      v-for="post in blogPosts"
      :key="post.id"
      class="bg-white/10 rounded-lg p-4 flex md:flex-row flex-col gap-4"
    >
      <NuxtImg
        :src="post.image"
        :alt="post.title"
        class="grow mb-4 rounded-lg object-cover border border-white/20 text-center aspect-video md:w-1/2"
      />

      <div>
        <h3 class="text-xl font-semibold mb-2 text-balance">{{ post.title }}</h3>
        <p class="text-sm text-white/80 mb-4">{{ post.excerpt }}</p>
        <a :href="`/blog/${post.id}`" class="text-green-500 hover:underline">Read Article</a>
      </div>
    </li>
  </ul>
</template>

<script lang="ts" setup>
import { blogPosts } from '@/data';
</script>
