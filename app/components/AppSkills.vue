<template>
  <section class="px-4 py-8 gap-8">
    <div class="text-center">
      <AppBadge>
        <div class="flex items-center gap-2">
          <IconSkills />
          Expertise
        </div>
      </AppBadge>

      <h2 class="text-5xl leading-tight font-thin my-8">Skills & Technologies</h2>

      <p class="mb-16 text-white/80">
        An overview of my technical skills and the technologies I have experience with.<br />
        I am always eager to learn new tools and frameworks to stay up-to-date with the latest industry trends.
      </p>
    </div>

    <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
      <div class="bg-slate-800 rounded-lg p-4">
        <h3 class="text-lg font-semibold mb-2 border-b border-white/20 pb-2">Frontend</h3>
        <ul class="text-white/80">
          <li>JavaScript</li>
          <li>TypeScript</li>
          <li>Vue.js</li>
          <li>Nuxt.js</li>
          <li>React</li>
          <li>Next.js</li>
          <li>HTML/CSS</li>
          <li>Tailwind CSS</li>
        </ul>
      </div>

      <div class="bg-slate-800 rounded-lg p-4">
        <h3 class="text-lg font-semibold mb-2 border-b border-white/20 pb-2">Backend & APIs</h3>
        <ul class="text-white/80">
          <li>Node.js</li>
          <li>NestJS</li>
          <li>Express</li>
          <li>Koa</li>
          <li>GraphQL</li>
          <li>REST APIs</li>
        </ul>
      </div>

      <div class="bg-slate-800 rounded-lg p-4">
        <h3 class="text-lg font-semibold mb-2 border-b border-white/20 pb-2">Databases</h3>
        <ul class="text-white/80">
          <li>MySQL</li>
          <li>PostgreSQL</li>
          <li>MongoDB</li>
          <li>Redis</li>
          <li>SQLite</li>
        </ul>
      </div>

      <div class="bg-slate-800 rounded-lg p-4">
        <h3 class="text-lg font-semibold mb-2 border-b border-white/20 pb-2">Tools & Others</h3>
        <ul class="text-white/80">
          <li>Git</li>
          <li>Docker</li>
          <li>AWS</li>
          <li>CI/CD</li>
          <li>Jest</li>
          <li>Webpack</li>
          <li>Vite</li>
          <li>Responsive Design</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
import AppBadge from '@/components/shared/AppBadge.vue';
import IconSkills from '@/components/icons/IconSkills.vue';
</script>
