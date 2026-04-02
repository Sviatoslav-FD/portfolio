<template>
  <button
    :type
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
		classes = 'rounded-full text-green-500 px-8 py-4 bg-slate-800 hover:bg-slate-700 font-semibold cursor-pointer'
	}

	return `${classes} ${props.disabled && 'cursor-not-allowed!'}`
})
</script>
