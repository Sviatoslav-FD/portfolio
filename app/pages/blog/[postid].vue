<template>
  <div class="m-8">
    <AppHeader />
    <div v-if="post" class="max-w-5xl mx-auto px-4">
      <h1 class="text-5xl font-thin text-center mb-8 text-balance">{{ post.title || 'Untitled Post' }}</h1>
      <p v-html="post?.article" />
      <ul>
        <li v-for="reference in references" :key="reference.id">
          <AppButton class="mt-4">
            <NuxtLink :to="`/blog/${reference.id}`">
              {{ reference.title }}
            </NuxtLink>
          </AppButton>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { blogPosts } from '@/data';
import { type TPost } from '@/types';
import AppButton from '~/components/shared/AppButton.vue';

const route = useRoute()

const post: Ref<TPost> = ref({} as TPost)
const references: Ref<TPost[]> = ref([] as TPost[])

onMounted(() => {
  post.value = blogPosts.find(p => p.id === route.params.postid) as TPost
  references.value = post.value.references?.map(ref => blogPosts.find(p => p.id === ref) as TPost) || []
})
</script>
