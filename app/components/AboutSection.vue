<template>
  <section role="region" aria-labelledby="about-section-title" id="about-section" class="px-4 py-8 flex gap-8">
    <div class="w-1/2">
      <AppBadge>
        <div class="flex items-center gap-4">
          <IconInfo />
          About Me
        </div>
      </AppBadge>
      <h2 id="about-section-title" class="text-5xl leading-tight font-thin my-8">Crafting Digital Experiences That Inspire</h2>
      <p class="mb-4 text-white/70">
        I am a passionate software engineer with over 8 years of experience in frontend and full-stack development. 
        My expertise lies in JavaScript, TypeScript, Vue, React, and Node.js, allowing me to create dynamic and responsive web applications.
        I thrive on solving complex problems and delivering high-quality solutions that enhance user experiences.
      </p>
      <p class="text-white/70 mb-8">
        Throughout my career, I have successfully completed over 50 projects, ranging from small startups to large enterprises. 
        I am committed to continuous learning and staying up-to-date with the latest technologies to ensure that my work remains innovative and effective.
      </p>

      <AppButton class="flex items-center gap-4">
        <IconDownload />
        Download Resume
      </AppButton>
    </div>

    <ul class="w-1/2" role="list" aria-label="List of skills and expertise">
      <li
        v-for="(item, index) in items"
        :key="index"
        class="mb-4 border border-green-700 rounded-lg px-4 py-2 cursor-pointer hover:bg-green-900 transition-colors duration-300"
        :class="openedIndex === index ? 'bg-green-900' : 'bg-slate-800'"
      >
        <h3
          class="text-lg cursor-pointer w-full flex items-center justify-between"
          :class="openedIndex === index ? 'text-green-500' : 'text-white/80'"
          @click="openedIndex === index ? openedIndex = -1 : openedIndex = index"
        >
          <span class="flex items-center gap-4">
            <component :is="item.icon" />
            {{ item.title }}
          </span>

          <IconArrowDown
            :class="openedIndex === index ? 'rotate-180 text-green-500' : 'text-white/80'"
            class="inline-block ml-2 transition-transform duration-300"
          />
        </h3>
        <p
          :class="openedIndex === index ? 'h-auto visible border-t border-green-500 mt-2 pt-2' : 'h-0 invisible'"
        >
          {{ item.description }}
        </p>
      </li>
    </ul>
  </section>
</template>

<script lang="ts" setup>
import AppBadge from '@/components/shared/AppBadge.vue';
import AppButton from '@/components/shared/AppButton.vue';
import IconInfo from '@/components/icons/IconInfo.vue';
import IconDownload from '@/components/icons/IconDownload.vue';
import IconArrowDown from '@/components/icons/IconArrowDown.vue';
import IconDevelopment from '@/components/icons/IconDevelopment.vue';
import IconTesting from '@/components/icons/IconTesting.vue';
import IconProjectManagement from '@/components/icons/IconProjectManagement.vue';
import IconLearning from '@/components/icons/IconLearning.vue';
import IconCollaboration from '@/components/icons/IconCollaboration.vue';
import IconProblemSolving from '@/components/icons/IconProblemSolving.vue';
import IconPerformanceOptimization from '@/components/icons/IconPerformanceOptimization.vue';
import IconSecurity from '@/components/icons/IconSecurity.vue';
import IconScalability from '@/components/icons/IconScalability.vue';
import IconAccessibility from '@/components/icons/IconAccessibility.vue';
import IconAnalytics from '@/components/icons/IconAnalytics.vue';
import IconUserExperience from '@/components/icons/IconUserExperience.vue';
import IconLeadership from '@/components/icons/IconLeadership.vue';

const items = [
  {
    icon: IconDevelopment,
    title: 'Development Expertise',
    description: 'Over 8 years of experience in frontend and full-stack development, specializing in JavaScript, TypeScript, Vue, React, and Node.js.'
  },
  {
    icon: IconTesting,
    title: 'Testing & Quality Assurance',
    description: 'Proficient in writing unit tests, integration tests, and end-to-end tests using tools like Jest, Cypress, and Testing Library.'
  },
  {
    icon: IconProjectManagement,
    title: 'Project Management',
    description: 'Experienced in Agile methodologies, including Scrum and Kanban, to manage projects efficiently and deliver high-quality results on time.'
  },
  {
    icon: IconLearning,
    title: 'Continuous Learning',
    description: 'Committed to staying up-to-date with the latest technologies and best practices in software development to ensure innovative and effective solutions.'
  },
  {
    icon: IconCollaboration,
    title: 'Collaboration',
    description: 'Strong team player with excellent communication skills, fostering collaboration and knowledge sharing among team members.'
  },
  {
    icon: IconProblemSolving,
    title: 'Problem Solving',
    description: 'Adept at analyzing complex problems and developing creative solutions that enhance user experiences and meet business goals.'
  },
  {
    icon: IconPerformanceOptimization,
    title: 'Performance Optimization',
    description: 'Skilled in optimizing web applications for performance, ensuring fast load times and smooth user interactions.'
  },
  {
    icon: IconSecurity,
    title: 'Security & Privacy',
    description: 'Knowledgeable in implementing security best practices and ensuring user data privacy in web applications.'
  },
  {
    icon: IconScalability,
    title: 'Architecture & Scalability',
    description: 'Experienced in designing scalable and maintainable software architectures that can grow with the needs of the business.'
  },
  {
    icon: IconAccessibility,
    title: 'Accessibility & Inclusivity',
    description: 'Passionate about creating accessible and inclusive web applications that provide a great user experience for all users, regardless of their abilities.'
  },
  {
    icon: IconAnalytics,
    title: 'SEO & Analytics',
    description: 'Familiar with SEO best practices and analytics tools to help improve the visibility and performance of web applications in search engines.'
  },
  {
    icon: IconUserExperience,
    title: 'User Experience',
    description: 'Focused on creating intuitive and engaging user interfaces that enhance the overall user experience and drive user satisfaction.'
  },
  {
    icon: IconLeadership,
    title: 'Leadership & Mentorship',
    description: 'Experienced in leading development teams and mentoring junior developers to help them grow their skills and advance their careers.'
  },
];

const openedIndex = ref(-1);
</script>
