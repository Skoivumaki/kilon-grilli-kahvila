<script setup lang="ts">

</script>

<template>
  <div class="flex flex-col lg:flex-row justify-center items-center h-fit w-full p-4">

    <div class="flex flex-col h-fit items-center bg-white lg:h-full">
      <div
        class="flex justify-center items-center font-karla text-xl font-bold w-full bg-secondary text-white p-4 gap-2 lg:p-4 lg:text-2xl">
        <i class="flex">
          <slot name="iconHeading"></slot>
        </i>
        <slot name="heading"></slot>
      </div>
      <div class="flex flex-row justify-between items-center pt-0">
        <i>
          <slot name="icon"></slot>
        </i>
        <i>
          <slot name="icon2"></slot>
        </i>
      </div>
    </div>

  </div>
</template>