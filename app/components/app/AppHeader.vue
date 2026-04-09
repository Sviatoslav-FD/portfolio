<template>
  <header
    ref="header"
    class="flex justify-between items-center md:p-4 p-2 bg-black/70 backdrop-blur-sm transition-all duration-300 z-10 relative"
    :class="isTopScrolled ? '' : 'fixed w-full top-0'"
    >

    <div
      class="md:hidden w-8 h-5 rounded-lg flex flex-col justify-between"
      @click="isMobileNavOpen = !isMobileNavOpen"
    >
      <div class="h-1 bg-green-500 rounded-lg" />
      <div class="h-1 bg-green-500 rounded-lg" />
      <div class="h-1 bg-green-500 rounded-lg" />
    </div>

    <NuxtLink
      to="/"
      class="md:visible hidden font-semibold text-3xl text-green-500"
      @mouseenter="isNameHovered = true"
      @mouseleave="isNameHovered = false"
    >
      Sviat<span
        class="text-black transition-colors duration-300"
        :class="isNameHovered && 'text-green-500'"
      >oslav
      </span>
    </NuxtLink>

    <nav
      class="absolute md:static top-full left-0 w-full md:w-auto bg-black/70"
      :class="isMobileNavOpen ? 'block' : 'hidden md:block'"
    >
      <ul class="md:flex font-thin text-3xl md:text-base">
        <li
          v-for="m in menu"
          :key="m.name"
          class="mx-2 my-4 md:my-0"
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
const isMobileNavOpen = ref(false)
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
