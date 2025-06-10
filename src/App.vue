<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed, watch } from 'vue'
import NavDesktop from './components/NavDesktop.vue'
import NavMobile from './components/NavMobile.vue'
import Home from './components/HomePage.vue'
import Menu from './components/MenuPage.vue'
import NotFound from './components/HomePage.vue'
import Gallery from './components/HomePage.vue'
import Contact from './components/HomePage.vue'
import Feedback from './components/HomePage.vue'
import FooterComponent from './components/CustomFooter.vue'

const isMobile = ref(false)
const dest = ref<string>()
const currentPath = ref(window.location.hash)

const routes = {
  '': Home || NotFound,
  'menu': Menu,
  'gallery': Gallery,
  'contact': Contact,
  'feedback': Feedback,
}

watch(dest, (newValue) => {
  if (newValue) {
    console.log("Destination changed to:", newValue)
    router(newValue)
  }
})

const router = (path: string) => {
  console.log("Navigating to:", dest.value)
  currentPath.value = `#/${path}`
  console.log("Currentpath to:", currentPath.value)
  console.log("CurrentView to:", currentView.value)
}

const currentView = computed(() => {
  const path = currentPath.value.replace(/^#\/?/, '')
  return routes[path as keyof typeof routes] || NotFound
})

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})


const checkIsMobile = () => {
  isMobile.value = window.matchMedia('(max-width: 767px)').matches
}

onMounted(() => {
  checkIsMobile()
  window.addEventListener('resize', checkIsMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkIsMobile)
})

</script>

<template>
  <header>
    <component :is="isMobile ? NavMobile : NavDesktop" v-model="dest" />
  </header>
  <main class="bg-cover ">
    <component :is="currentView" />
  </main>
  <footer>
    <FooterComponent class="" :details="'Lansanpurontie 13\n02610 Espoo\nSähköposti?\n040 3200646'" :days="[
      'Maanantai',
      'Tiistai',
      'Keskiviikko',
      'Torstai',
      'Perjantai',
      'Lauantai',
      'Sunnuntai'
    ]" :hours="[
      '14:00-21:00',
      '14:00-21:00',
      '14:00-21:00',
      '14:00-21:00',
      '14:00-22:00',
      '11:00-22:00',
      '11:00-21:00'
    ]">
      <template #contactHeading>Yhteystiedot</template>
      <template #timesHeading>Aukioloajat</template>
      <template #author>Copyright © 2025 Kilon Grilli-Kahvila Oy</template>
    </FooterComponent>
  </footer>
</template>

<style scoped>
.logo {
  display: block;
  margin: 0 auto 2rem;
}

main {
  max-width: 1920px;
  padding-top: 8rem;
  margin: 0 auto;
  background-image: url('./assets/bg.jpg');
}

@media (min-width: 480px) {
  main {
    max-width: 1920px;
  }
}
</style>
