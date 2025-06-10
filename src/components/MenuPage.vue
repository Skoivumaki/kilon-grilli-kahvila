<script setup lang="ts">
import CarIcon from './icons/IconCar.vue'
import ContainerButtons from './ContainerButtons.vue'
import ContainerImages from './ContainerImages.vue'
import SpacerHeader from './SpacerHeader.vue'
import SpacerImage from './SpacerImage.vue'
import Pizza from '../assets/bg.jpg'
import Kebab from '../assets/bg2.jpg'
import Burger from '../assets/burgir.webp'
import MenuItem from './MenuItem.vue'

//mock remote data
const menuItems = [
  { id: 1, name: "Julia", ingredients: "Kinkku, ananas", price: 13.00 },
  { id: 2, name: "Frutti di mare", ingredients: "Tonnikala, katkarapu", price: 13.00 },
  { id: 3, name: "Quattro", ingredients: "Kinkku, herkkusieni, paprika", price: 13.00 },
  { id: 4, name: "Pronto", ingredients: "Salami, sipuli, herkkusieni", price: 13.00 },
  { id: 5, name: "Vegan", ingredients: "Ananas, herkkusieni, olivi", price: 13.00 },
  { id: 6, name: "Italiano", ingredients: "Kinkku, aurinkokuivattu tomaatti, mozzarella", price: 13.00 },
];

const menuItems2 = [
  { id: 7, name: "Kebab ranskalaisilla", ingredients: "Ranskalaiset, valitsemasi kebabliha, salaatti, kebab- ja valkosipulijogurttikastike", price: 13.00 },
  { id: 8, name: "Rullakebab", ingredients: "Pizzapohja, valitsemasi kebabliha, salaatti, kebab- ja valkosipulijogurttikastike", price: 13.00 },
  { id: 9, name: "Leipäkebab", ingredients: "Talon leipä, valitsemasi kebabliha, salaatti, kebab- ja valkosipulijogurttikastike", price: 13.00 },
  { id: 10, name: "Kebabsalaatti", ingredients: "Runsasti salaattia, valitsemasi kebabliha, kebab- ja valkosipulijogurttikastike", price: 13.00 },
];

const menuItems3 = [
  { id: 11, name: "Talon XL Burger", ingredients: "Naudan jauhelihapihvi, cheddarjuusto, maustekurkku, sipuli, tomaatti, salaatti", price: 13.00 },
  { id: 12, name: "Talon Kana Burger", ingredients: "Kanapihvi, cheddarjuusto, maustekurkku, sipuli, tomaatti, salaatti", price: 13.00 },
];


</script>

<template class="w-[100vw]">
  <div class="lg:flex lg:flex-row items-strech">
    <ContainerButtons>
      <template #iconHeading>
        <DocumentationIcon />
      </template>
      <template #heading>Soita ja nouda</template>
    </ContainerButtons>
    <ContainerImages>
      <template #iconHeading>
        <CarIcon />
      </template>
      <template #heading>Kotiinkuljetus</template>
      <template #icon>
        <img alt="Kilon Grilli-Kahvila Logo" class="w-[50vw]" src="../assets/foodora.png" />
      </template>
      <template #icon2>
        <img alt="Kilon Grilli-Kahvila Logo" class="w-[50vw]" src="../assets/wolt.jpeg" />
      </template>
    </ContainerImages>
  </div>
  <SpacerHeader>
    <template #heading>Menu</template>
  </SpacerHeader>
  <SpacerImage :image="Pizza">
    <template #heading>Pizzat</template>
  </SpacerImage>
  <div class="flex flex-col justify-center items-center w-full p-4 gap-4 bg-secondary">
    <MenuItem class="" v-for="(item, index) in menuItems" :key="index" :id="item.id" :name="item.name"
      :ingredients="item.ingredients" :price="item.price">
    </MenuItem>
  </div>
  <SpacerImage :image="Kebab">
    <template #heading>Kebabit</template>
  </SpacerImage>
  <div class="flex flex-col justify-center items-center w-full p-4 gap-4 bg-secondary">
    <MenuItem class="" v-for="(item, index) in menuItems2" :key="index" :id="item.id" :name="item.name"
      :ingredients="item.ingredients" :price="item.price">
    </MenuItem>
  </div>
  <SpacerImage :image="Burger">
    <template #heading>Burgerit</template>
  </SpacerImage>
  <div class="flex flex-col justify-center items-center w-full p-4 gap-4 bg-secondary">
    <MenuItem class="" v-for="(item, index) in menuItems3" :key="index" :id="item.id" :name="item.name"
      :ingredients="item.ingredients" :price="item.price">
    </MenuItem>
  </div>
  <SpacerImage :image="Pizza">
    <template #heading>Grilliruoka</template>
  </SpacerImage>
</template>
