<script setup lang="ts">
import { ref, type Ref } from 'vue'

let windowWidth: Ref<number> = ref(window.innerWidth)

const setWindowWidth = () => (windowWidth.value = window.innerWidth)

window.addEventListener('resize', setWindowWidth)
</script>

<template>
	<div class="bg-image" v-if="windowWidth > 1099" role="img" aria-label="background image"></div>
</template>

<style lang="scss">
@use 'sass:map';
@import '../styles/variables';

.bg-image {
	background: map-get($bg, 'illustration');
	background-repeat: no-repeat;
	background-size: contain;

	width: 400px;
	height: 330px;
}
</style>
