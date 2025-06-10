<script setup lang="ts">
defineProps<{ image: string }>();
</script>

<template>
  <div class="flex flex-col h-fit items-center bg-white lg:h-full">
    <div
      class="flex justify-center items-center font-karla text-xl font-bold w-full h-30 bg-secondary background text-white text-shadow-md/20 p-4 gap-2 lg:text-2xl bg-cover bg-center"
      :style="{ backgroundImage: `linear-gradient(360deg, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.25) 100%), url('${image}')` }">
      <slot name="heading"></slot>
    </div>
  </div>
</template>