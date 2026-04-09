<template>
  <div class="bg-slate-800 rounded-lg p-4 border border-green-700">
    <h3 class="text-xl font-thin mb-4 border-b border-green-700 pb-2">
      {{ title }}
    </h3>

    <ul class="text-white/80">
      <SkillsModuleItem v-for="skill in skills" :key="skill.name" :skill />
    </ul>
  </div>
</template>

<script lang="ts" setup>
import SkillsModuleItem from '@/components/skills/SkillsModuleItem.vue';

defineProps<{
  title: string;
  skills: {
    name: string;
    experience: string;
    proficiency: string;
  }[];
}>();
</script>
