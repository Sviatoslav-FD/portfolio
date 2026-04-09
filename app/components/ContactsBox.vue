<template>
  <div class="mb-2 bg-green-700/20 md:p-4 p-2 rounded-lg border border-green-700 flex items-center gap-4">
    <div class="bg-green-500/50 p-2 rounded-lg">
      <slot name="icon" />
    </div>

    <div>
      <p class="text-xs text-white/80">{{ label }}:</p>
      <a :href="href" :target="href.startsWith('http') ? '_blank' : '_self'">
        <slot>{{ href.split(':')[1] }}</slot>
      </a>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  label: string;
  href: string;
}>();
</script>
