<template>
  <section role="region" aria-labelledby="contact-section-title" id="contact-section" class="px-4 py-8 gap-8">
    <div class="text-center">
      <AppBadge>
        <div class="flex items-center gap-2">
          <IconContact />
          Contacts
        </div>
      </AppBadge>

      <h2 id="contact-section-title" class="text-5xl leading-tight font-thin my-8">Let's Work Together</h2>

      <p class="mb-16 text-white/80">
        I'm always open to new opportunities and collaborations.<br />
        Whether you have a project in mind, want to discuss potential partnerships, or just want to say hello, feel free to reach out.
      </p>
    </div>

    <div class="flex gap-8">
      <form class="w-1/2 rounded-lg bg-slate-800 p-8 border border-green-700">
        <div class="mb-4">
          <label for="name" class="block text-sm font-medium mb-1">Name</label>
          <input type="text" id="name" class="w-full px-3 py-2 rounded-md bg-white/20 focus:bg-white/30 focus:outline-none transition duration-200" placeholder="Your Name" />
        </div>

        <div class="mb-4">
          <label for="email" class="block text-sm font-medium mb-1">Email</label>
          <input type="email" id="email" class="w-full px-3 py-2 rounded-md bg-white/20 focus:bg-white/30 focus:outline-none transition duration-200" placeholder="Your Email" />
        </div>

        <div class="mb-4">
          <label for="message" class="block text-sm font-medium mb-1">Message</label>
          <textarea id="message" rows="5" class="w-full px-3 py-2 rounded-md bg-white/20 focus:bg-white/30 focus:outline-none transition duration-200" placeholder="Your Message" />
        </div>

        <AppButton type="submit" class="w-full">
          Send Message
        </AppButton>
      </form>

      <div class="w-1/2">
        <h3 class="text-4xl leading-tight font-thin">Let's Connect</h3>
        <p class="my-4 text-white/80">
          I'm always open to discussing new projects, creative ideas, or opportunities to be part of your visions.<br />
          Feel free to reach out through any of the following methods:
        </p>

        <ContactsBox label="Email" href="mailto:sviatoslavpanevnyk@com.com">
          <template #icon><IconEmail /></template>
        </ContactsBox>

        <ContactsBox label="Phone" href="tel:+380935178555">
          <template #icon><IconPhone /></template>
          +38 (093) 51-78-555
        </ContactsBox>

        <ContactsBox label="Location" href="https://maps.app.goo.gl/cnE3FPyqAXopRu9x9">
          <template #icon><IconLocation /></template>
          Stryi, Lviv, Ukraine
        </ContactsBox>

        <ContactsBox label="LinkedIn" href="https://www.linkedin.com/in/sviatoslavpanevnyk/">
          <template #icon><IconLinkedIn /></template>
          Sviatoslav Panevnyk
        </ContactsBox>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
import AppBadge from '@/components/shared/AppBadge.vue';
import IconContact from '@/components/icons/IconContact.vue';
import IconLocation from '@/components/icons/IconLocation.vue';
import IconEmail from '@/components/icons/IconEmail.vue';
import IconPhone from '@/components/icons/IconPhone.vue';
import IconLinkedIn from '@/components/icons/IconLinkedIn.vue';
import AppButton from './shared/AppButton.vue';
</script>
