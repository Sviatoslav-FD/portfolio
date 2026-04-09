<template>
  <header
    ref="header"
    class="flex justify-between items-center p-4 bg-black/70 backdrop-blur-sm transition-all duration-300 z-10"
    :class="isTopScrolled ? '' : 'fixed w-full top-0'"
    >
    <NuxtLink
      to="/"
      class="font-semibold text-3xl text-green-500"
      @mouseenter="isNameHovered = true"
      @mouseleave="isNameHovered = false"
    >
      Sviat<span
        class="text-black transition-colors duration-300"
        :class="isNameHovered && 'text-green-500'"
      >oslav
      </span>
    </NuxtLink>

    <nav>
      <ul class="flex">
        <li
          v-for="m in menu"
          :key="m.name"
          class="mx-2"
        >
          <a :href="m.href" class="hover:underline hover:text-green-500 transition-colors duration-300">{{ m.name }}</a>
        </li>
      </ul>
    </nav>

    <AppButton>
      Contact Me
    </AppButton>
  </header>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import AppButton from '@/components/shared/AppButton.vue'

const isNameHovered = ref(false)
const isTopScrolled = ref(true)
const headerRef = useTemplateRef<HTMLElement | null>('header')

const menu = [
  { name: 'Home', href: '#main-section' },
  { name: 'About', href: '#about-section' },
  { name: 'Skills', href: '#skills-section' },
  { name: 'Projects', href: '#' },
  { name: 'Blog', href: '#blog-section' },
  { name: 'Contact', href: '#contact-section' },
]

const topScroll = () => {
  if (headerRef.value) {
    if (window.scrollY > 50) {
      isTopScrolled.value = false
    } else {
      isTopScrolled.value = true
    }
  }
}

onMounted(() => {
  document.addEventListener('scroll', topScroll)
})

onUnmounted(() => {
  document.removeEventListener('scroll', topScroll)
})
</script>
