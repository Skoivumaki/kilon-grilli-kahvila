<script setup lang="ts">
import { ref } from 'vue'

const isOpen = ref(false)

const toggleMenu = () => {
  isOpen.value = !isOpen.value
}
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

const isOpenLang = ref(false)

const toggleMenuLang = () => {
  isOpenLang.value = !isOpenLang.value
}
</script>

<template>
  <!-- Main Nav Container -->
  <nav class="flex flex-col fixed top-0 w-full bg-secondary z-1 transition-all duration-300 ease-in-out">
    <div class="flex flex-col w-full h-fit bg-secondary z-0 transition-all duration-300 ease-in-out">
      <div class="flex items-center justify-center w-full h-20 px-5 border-secondary-alt border-b-2">
        <span class="w-full h-[46px] flex items-center justify-center">
        </span>
        <button class="w-60 flex items-center justify-center">
          <img alt="Kilon Grilli-Kahvila Logo" class="logo" src="../assets/logo.png" />
        </button>
        <span class="w-full h-[46px] flex justify-end">
          <span class="w-10 h-[46px]">
            <button class="flex items-center justify-end w-full h-full" @click="toggleMenu">
              <img v-if="!isOpen" alt="Menu Open" class="logo" src="../assets/hamburger.svg" width="25" height="25" />
              <img v-else alt="Menu Close" class="logo" src="../assets/close.svg" width="25" height="25" />
            </button>
          </span>
        </span>
      </div>
      <div :class="[
        'transition-all duration-300 ease-in-out flex flex-col items-center w-full bg-secondary overflow-hidden',
        isOpen ? 'max-h-90' : 'max-h-0'
      ]">
        <button @click="navigate('home')"
          class="text-white active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center justify-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt">
          Koti
        </button>
        <button @click="navigate('menu')"
          class="text-white active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center justify-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt">
          Menu
        </button>
        <button @click="navigate('gallery')"
          class="text-white active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center justify-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt">
          Galleria
        </button>
        <button @click="navigate('contact')"
          class="text-white active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center justify-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt">
          Ota yhteyttä
        </button>
        <button @click="navigate('feedback')"
          class="text-white active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center justify-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt">
          Palaute
        </button>
        <button @click="toggleMenuLang"
          class="w-full h-[46px] flex font-bold text-xl flex-row justify-between text-white items-center px-5 border-b-2 border-secondary-alt">
          <span class="flex flex-row gap-2 ">
            <img alt="Vue logo" class="logo" src="../assets/globe.svg" width="25" height="25" />
            Kieli
          </span>

          <img v-if="!isOpenLang" alt="Vue logo" class="logo" src="../assets/chevrondown.svg" width="25" height="25" />
          <img v-else alt="Vue logo" class="logo" src="../assets/close.svg" width="25" height="25" />
        </button>
        <div :class="[
          'transition-all duration-300 ease-in-out flex flex-col items-center w-full bg-secondary overflow-hidden',
          isOpenLang ? 'max-h-30' : 'max-h-0'
        ]">
          <span
            class="text-white pl-5 active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt">
            Suomi
          </span>
          <span
            class="text-white pl-5 active:text-primary transition-colors duration-300 font-bold text-xl text-center font-karla w-full h-15 flex items-center active:bg-secondary-alt hover:text-primary transition-colors duration-300 border-b-2 border-secondary-alt height-transition">
            Englanti
          </span>
        </div>
      </div>

    </div>
  </nav>

</template>

<style scoped></style>
