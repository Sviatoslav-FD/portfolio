<template>
  <section role="region" aria-labelledby="skills-section-title" id="skills-section" class="px-4 py-8 gap-8">
    <div class="text-center">
      <AppBadge>
        <div class="flex items-center gap-2">
          <IconSkills />
          Expertise
        </div>
      </AppBadge>

      <h2 id="skills-section-title" class="text-5xl leading-tight font-thin my-8">Skills & Technologies</h2>

      <p class="mb-16 text-white/80">
        An overview of my technical skills and the technologies I have experience with.<br />
        I am always eager to learn new tools and frameworks to stay up-to-date with the latest industry trends.
      </p>
    </div>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
      <SkillsModule :skills="frontend" title="Frontend" />
      <SkillsModule :skills="backend" title="Backend & APIs" />
      <SkillsModule :skills="databases" title="Databases" />
      <SkillsModule :skills="tools" title="Tools & Others" />
    </div>
  </section>
</template>

<script lang="ts" setup>
import AppBadge from '@/components/shared/AppBadge.vue';
import IconSkills from '@/components/icons/IconSkills.vue';
import SkillsModule from '@/components/skills/SkillsModule.vue';
import { frontend, backend, databases, tools } from '@/data';
</script>
