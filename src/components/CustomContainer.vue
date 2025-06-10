<script setup lang="ts">

</script>

<template>
  <div class="flex flex-col lg:flex-row justify-center items-center h-fit w-full p-4">

    <div class="flex flex-col h-fit items-center bg-white lg:h-full">
      <div
        class="flex justify-center font-karla text-xl font-bold w-full bg-secondary text-white p-4 gap-2 lg:p-4 lg:text-2xl">
        <i class="flex items-center">
          <slot name="iconHeading"></slot>
        </i>
        <slot name="heading"></slot>
      </div>
      <div class="flex text-center text-lg items-center text-secondary lg:text-xl p-6">
        <slot name="description"></slot>
      </div>
    </div>

  </div>
</template>