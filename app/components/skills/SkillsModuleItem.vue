<template>
  <li class="flex items-center gap-4 mb-4">
    <div class="w-10 h-10 bg-green-500/30 rounded flex items-center justify-center">
      <component
        v-if="skill.icon"
        :is="skill.icon"
        class="w-5 h-5 text-green-500"
      />
    </div>

    <div class="grow">
      <p class="text-sm font-medium">
        {{ skill.name }}
      </p>
      <p class="text-xs">{{ skill.experience }}</p>
    </div>
    <AppBadge class="text-xs px-2! py-0!">{{ skill.proficiency }}</AppBadge>
  </li>
</template>

<script lang="ts" setup>
import IconDevelopment from '@/components/icons/IconDevelopment.vue';
import AppBadge from '@/components/shared/AppBadge.vue';

defineProps<{
  skill: {
    icon?: string;
    name: string;
    experience: string;
    proficiency: string;
  };
}>();
</script>
