<script setup lang="ts">

import Button from './ButtonComponent.vue'
defineProps<{ name: string; message: string; phone: string; email: string }>();
defineEmits(['update:name', 'update:email', 'update:phone', 'update:message', 'submit']);
</script>

<template>
  <div id="feedback" class="flex bg-secondary h-fit">
    <div class="flex flex-col lg:flex-row flex-nowrap justify-center items-center w-full p-4 gap-4">
      <div class="w-fit h-full">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d853.4939055519103!2d24.779570403867368!3d60.21699149408411!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x468df50039cf2829%3A0x545fd49a11e19317!2sKilon%20Grilli-Kahvila!5e1!3m2!1sfi!2sfi!4v1749551128746!5m2!1sfi!2sfi"
          class="w-[90vw] lg:w-md h-[90vw] lg:h-full" width=[100vw] height=[100vw] style="border:0;" loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
      <div class="flex flex-col items-center w-full lg:basis-lg bg-white gap-2 *:p-3 *:w-full">
        <div>
          <h1 class="flex text-primary font-karla text-2xl font-bold justify-center">Palaute</h1>
        </div>
        <div
          class="flex flex-col gap-4 *:p-2 *:border-b-2 *:border-primary *:focus:outline-none *:focus:inset-shadow-xs *:inset-shadow-primary/100 *:focus:bg-primary/10">
          <input :value="name" @input="$emit('update:name', ($event.target as HTMLInputElement).value)"
            placeholder="Nimi" />
          <input :value="email" @input="$emit('update:email', ($event.target as HTMLInputElement).value)"
            placeholder="Sähköposti" />
          <input :value="phone" @input="$emit('update:phone', ($event.target as HTMLInputElement).value)"
            placeholder="Puhelin" />
          <textarea :value="message" @input="$emit('update:message', ($event.target as HTMLInputElement).value)"
            placeholder="Viesti"></textarea>
        </div>
        <div class="flex justify-center w-100">
          <Button variant="primary" @click="$emit('submit')">
            <template #heading> Lähetä </template>
          </Button>
        </div>
      </div>
    </div>
  </div>
</template>