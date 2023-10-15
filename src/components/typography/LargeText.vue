<script setup lang="ts">
type Props = {
  aligment: AlignSetting
}

defineProps<Props>()
</script>

<template>
  <h1><slot /></h1>
</template>

<style lang="scss">
@use 'sass:map';
@import '../../styles/variables';

h1 {
  width: 100%;
  color: map-get($colors, 'dark', '10');
  @include typography('display-lg');
}
</style>
