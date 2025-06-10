<script setup lang="ts">

</script>

<template>
  <div class="flex flex-col h-fit items-center bg-white lg:h-full">
    <div
      class="flex justify-center font-karla text-xl font-bold w-full bg-secondary text-white p-4 gap-2 lg:p-4 lg:text-2xl">
      <i class="flex items-center">
        <slot name="iconHeading"></slot>
      </i>
      <slot name="heading"></slot>
    </div>

  </div>
</template>