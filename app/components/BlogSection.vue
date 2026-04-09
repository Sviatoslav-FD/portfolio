<template>
  <section
    id="blog-section"
    class="px-4 py-8 gap-8"
    role="region"
    aria-labelledby="blog-section-title"
  >
    <div class="text-center">
      <AppBadge>
        <div class="flex items-center gap-2">
          <IconBlog />
          Blog
        </div>
      </AppBadge>

      <h2
        id="blog-section-title"
        class="md:text-5xl text-3xl font-thin md:my-8 my-4 text-balance"
      >
        Latest Blog Posts
      </h2>

      <p class="md:mb-16 mb-8 text-white/80 text-balance">
        An overview of my latest blog posts and articles.<br />
        I share insights, tutorials, and updates on web development, programming, and technology trends.
      </p>
    </div>

    <ul class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
      <li
        v-for="post in blogPosts.slice(0, 6)"
        :key="post.id"
        class="bg-green-700/20 border border-green-500 rounded-lg p-4 md:aspect-square flex flex-col"
      >
        <h3 class="text-xl font-semibold mb-2 text-balance">{{ post.title }}</h3>
        <p class="text-sm text-white/80 mb-4 truncate">{{ post.excerpt }}</p>
        <div class="grow mb-4 rounded-lg bg-white/9 text-center aspect-video md:block hidden">
          <NuxtImg
            v-if="post.image"
            :src="post.image"
            :alt="post.title"
            class="object-cover w-full h-full rounded-lg"
          />
          <p
            v-else
            class="text-xl font-thin text-white/50 p-4 text-balance"
          >
            Would be great to add an image here.
          </p>
        </div>
        <a :href="`/blog/${post.id}`" class="text-green-500 hover:underline">Read Article</a>
      </li>
    </ul>

    <AppButton class="mx-auto mt-8 block" @click="navigateTo('/blog')">
      View All Posts
    </AppButton>
  </section>
</template>

<script lang="ts" setup>
import AppBadge from '@/components/shared/AppBadge.vue';
import AppButton from '@/components/shared/AppButton.vue';
import IconBlog from '@/components/icons/IconBlog.vue';

import { blogPosts } from '@/data';
</script>
