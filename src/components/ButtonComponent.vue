<script setup lang="ts">
defineProps<{
  variant?: 'primary' | 'secondary';
  link?: string;
}>()
</script>

<template>
  <button :v-if="link ? 'a' : 'button'" :href="link" :class="[
    'flex justify-center items-center text-xl font-bold transition-colors duration-300 min-w-50 md:min-w-80 w-fit p-5 gap-2 rounded-4xl lg:p-4 lg:text-2xl',
    variant === 'primary'
      ? 'bg-primary text-white border-2 border-white hover:bg-white hover:text-primary hover:border-primary active:bg-white active:text-primary'
      : 'bg-white text-primary border-2 border-primary hover:bg-primary hover:text-white active:bg-primary active:text-white'
  ]">
    <i class="flex items-center transition duration-0 text-inherit fill-current stroke-current">
      <slot name="iconHeading"></slot>
    </i>
    <slot name="heading"></slot>
  </button>
</template>