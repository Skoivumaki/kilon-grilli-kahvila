<script setup lang="ts">

const model = defineModel()

const navigate = (dest: string) => {
  // Scroll to the destination element if exists
  const element = document.getElementById(dest);
  if (element) {
    console.log("Navigating to :", element);
    element?.scrollIntoView({
      behavior: "smooth",
      block: "start",
      inline: "nearest"
    });
  } else {
    // Emit the destination to the parent component if doesn't exist
    console.log("Destination not found, emitting:", dest);
    model.value = dest;
  }
}

</script>

<template>
  <!-- Main Nav Container -->
  <nav
    class="flex flex-col sm:fixed top-0 w-full h-[8rem] bg-secondary flex flex-row justify-between z-1 shadow-2xs shadow-primary/100">
    <div class="flex flex-col sm:w-full h-full bg-secondary flex flex-row items-center z-0">
      <div class="flex items-center justify-center px-[35px] gap-[10px] w-60 h-10">
        <span class="w-full flex items-center justify-center">
          <img alt="Vue logo" class="logo" src="../assets/logo.png" />
        </span>
      </div>

      <!-- Frame 18: Koti -->
      <button @click="navigate('home')"
        class="flex items-center justify-center w-[150px] h-full bg-secondary hover:bg-secondary-alt hover:text-primary transition-colors duration-300">
        <span
          class="text-white hover:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-full flex items-center justify-center">
          Koti
        </span>
      </button>

      <!-- Frame 19: Menu -->
      <button @click="navigate('menu')"
        class="flex items-center justify-center w-[150px] h-full bg-secondary hover:bg-secondary-alt hover:text-primary transition-colors duration-300">
        <span
          class="text-white hover:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-full flex items-center justify-center">
          Menu
        </span>
      </button>
      <!-- Frame 20: Galleria -->
      <button @click="navigate('gallery')"
        class="flex items-center justify-center w-[150px] h-full bg-secondary hover:bg-secondary-alt hover:text-primary transition-colors duration-300">
        <span
          class="text-white hover:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-full flex items-center justify-center">
          Galleria
        </span>
      </button>
      <!-- Frame 21: Ota yhteyttä -->
      <button @click="navigate('feedback')"
        class="flex items-center justify-center w-[150px] h-full bg-secondary hover:bg-secondary-alt hover:text-primary transition-colors duration-300">
        <span
          class="text-white hover:text-primary transition-colors duration-300 font-bold text-xl text-center leading-normal font-karla w-full h-full flex items-center justify-center">
          Ota yhteyttä
        </span>
      </button>
      <!-- Frame 22: Palaute -->
      <button @click="navigate('feedback')"
        class="flex items-center justify-center w-[150px] h-full bg-secondary hover:bg-secondary-alt hover:text-primary transition-colors duration-300">
        <span
          class="text-white hover:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-full flex items-center justify-center">
          Palaute
        </span>
      </button>
      <!-- Frame 16: Language Selector -->
    </div>
    <div class="flex items-center px-[25px] gap-[20px] w-[200px] h-[125px] bg-secondary z-[2]">
      <div
        class="text-white hover:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-full flex items-center justify-center gap-2">
        <!-- Vector (icon) -->
        <div class="w-[20px] h-[20px]">
          <img alt="Vue logo" class="logo" src="../assets/globe.svg" width="25" height="25" />
        </div>
        <!-- Kieli -->
        <span
          class="text-white font-bold text-[20px] leading-[23px] text-center font-karla w-[43px] h-[23px] flex items-center justify-center">
          Kieli
        </span>

        <!-- Frame (arrow or dropdown indicator) -->
        <div class="w-[25px] h-[15px] flex items-center justify-center">
          <img alt="Vue logo" class="logo" src="../assets/chevrondown.svg" width="20" height="20" />
        </div>
      </div>
    </div>
  </nav>

</template>

<style scoped>
@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
