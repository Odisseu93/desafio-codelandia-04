<script setup lang="ts">
import type { InputHTMLAttributes } from 'vue'

const uuid = crypto.randomUUID()

type Props = {
	label?: string
	type: InputHTMLAttributes['type']
	placeholder?: string
	value?: InputHTMLAttributes['value']
	required?: boolean
}

defineProps<Props>()
</script>

<template>
	<div class="form-control">
		<label :for="uuid">{{ label }}</label>
		<input :id="uuid" :required="required" :value="value" :placeholder="placeholder" :type="type" />
	</div>
</template>

<style lang="scss">
@import '../../styles/variables';

label {
	display: block;
	width: 100%;

	line-height: 2rem;
}

input {
	width: 100%;

	padding-block: 0.5rem;
	padding-inline: 0.8rem;
	border: none;
}
</style>
