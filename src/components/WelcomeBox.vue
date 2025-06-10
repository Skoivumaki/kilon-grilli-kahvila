<script setup lang="ts">
import Container from './CustomContainer.vue'
</script>

<template>
  <div class="flex flex-col lg:flex-row justify-center items-center lg:w-full">
    <i>
      <slot name="icon"></slot>
    </i>
    <Container>
      <template #heading>
        <slot name="heading"></slot>
      </template>
      <template #description>
        <slot name="description"></slot>
      </template>
    </Container>
  </div>
</template>