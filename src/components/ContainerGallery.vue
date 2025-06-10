<script setup lang="ts">

// images2 = [
//   '../assets/logo.png',
// ];
</script>

<template>
  <div id="gallery" class="flex bg-white h-fit">
    <div class="flex flex-row flex-wrap justify-center items-center w-full p-4 gap-4">
      <div class="p-4 basis-3xs lg:basis-lg">
        <img alt="Kilon Grilli-Kahvila Logo"
          class="rounded-2xl shadow-xl transition-transform duration-300 hover:scale-105"
          src="../assets/outside.webp" />
      </div>
      <div class="p-4 basis-3xs lg:basis-lg">
        <img alt="Kilon Grilli-Kahvila Logo"
          class="rounded-2xl shadow-xl transition-transform duration-300 hover:scale-105"
          src="../assets/outside.webp" />
      </div>
      <div class="p-4 basis-3xs lg:basis-lg">
        <img alt="Kilon Grilli-Kahvila Logo"
          class="rounded-2xl shadow-xl transition-transform duration-300 hover:scale-105" src="../assets/logo.png" />
      </div>
    </div>
  </div>
</template>