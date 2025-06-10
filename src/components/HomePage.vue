<script setup lang="ts">
import { ref } from 'vue';
import CarIcon from './icons/IconCar.vue'
import IconCall from './icons/IconCall.vue'
import WelcomeBox from './WelcomeBox.vue'
import ContainerButtons from './ContainerButtons.vue'
import ContainerImages from './ContainerImages.vue'
import SpacerHeader from './SpacerHeader.vue'
import ContainerGallery from './ContainerGallery.vue'
import Contact from './ContactForm.vue'

const name = ref('');
const email = ref('');
const phone = ref('');
const message = ref('');

const submitForm = () => {
  console.log({ name: name.value, email: email.value, phone: phone.value, message: message.value });
};
</script>

<template>
  <div id="home" class="flex flex-col lg:flex-row">
    <WelcomeBox>
      <template #icon>
        <img alt="Kilon Grilli-Kahvila Logo" class="logo" src="../assets/logo.png" />
      </template>
      <template #heading>Tervetuloa Kilon Grilli-Kahvilaan!</template>
      <template #description>
        Herkuilla ei ole kiirettä – mutta nälällä on!
        Kilon Grilli-Kahvila tarjoaa maistuvat grilliruoat, pizzat, burgerit, tuoreet kahvit ja mutkatonta palvelua
        Espoon
        sydämessä. Olitpa
        matkalla töistä kotiin tai hakemassa lounasta, meiltä saat vatsan täyteen ja hymyn huulille.
      </template>
    </WelcomeBox>
  </div>
  <div class="lg:flex lg:flex-row items-strech">
    <ContainerButtons>
      <template #iconHeading>
        <IconCall />
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
    <template #heading>Galleria</template>
  </SpacerHeader>
  <ContainerGallery>
  </ContainerGallery>
  <SpacerHeader>
    <template #heading>Ota yhteyttä</template>
  </SpacerHeader>
  <Contact :name="name" @update:name="name = $event" :email="email" @update:email="email = $event" :phone="phone"
    @update:phone="phone = $event" :message="message" @update:message="message = $event" @submit="submitForm" />
</template>
