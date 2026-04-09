<template>
  <button
    :type
		class="text-nowrap"
    :class="classes"
    :disabled
  >
    <slot />
  </button>
</template>

<script setup lang="ts">
interface Props {
	type?: 'button' | 'submit' | 'reset'
	variant?: 'primary'
	disabled?: boolean
}

const props = withDefaults(defineProps<Props>(), {
	type: 'button',
	variant: 'primary',
	disabled: false,
})

const classes = computed<string>(() => {
	let classes = ''

	if (props.variant === 'primary') {
		classes = 'rounded-full text-green-500 md:px-8 md:py-4 px-4 py-2 bg-green-700/20 hover:bg-green-700/40 font-semibold cursor-pointer border border-green-500 transition-colors duration-300'
	}

	return `${classes} ${props.disabled && 'cursor-not-allowed!'}`
})
</script>
