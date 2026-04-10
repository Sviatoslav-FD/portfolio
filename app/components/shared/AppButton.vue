<template>
  <button
    :type
		class="rounded-full text-green-500 md:px-8 md:py-4 px-4 py-2 bg-green-700/50 hover:bg-green-700/20 font-semibold cursor-pointer border border-green-500 transition-colors duration-300 text-nowrap"
    :class="disabled && 'cursor-not-allowed!'"
    :disabled
  >
    <slot />
  </button>
</template>

<script setup lang="ts">
interface Props {
	type?: 'button' | 'submit' | 'reset'
	disabled?: boolean
}

withDefaults(defineProps<Props>(), {
	type: 'button',
	variant: 'primary',
	disabled: true,
})
</script>
