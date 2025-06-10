<script setup lang="ts">
defineProps({
  details: String,
  days: Array,
  hours: Array,
})
</script>

<template>
  <div class="h-[1rem] bg-primary" />
  <div class="flex flex-col h-fit items-center p-2 bg-white">
    <div class="font-karla text-xl font-bold text-primary p-2">
      <slot name="contactHeading"></slot>
    </div>
    <div class="flex text-center items-center whitespace-pre-line text-secondary">
      {{ details }}
    </div>
    <div class="font-karla text-xl font-bold text-primary p-2">
      <slot name="timesHeading"></slot>
    </div>
    <div class="flex flex-row text-secondary h-fit">
      <div class="flex flex-col text-secondary">
        <div v-for="(day, index) in days" :key="index" class="flex w-50 justify-end pr-2">
          <span>{{ day }}</span>
        </div>
      </div>
      <div class="flex flex-col text-secondary h-fit">
        <div v-for="(hours, index) in hours" :key="index" class="flex w-50 justify-start pl-2">
          <span>{{ hours }}</span>
        </div>
      </div>
    </div>
    <div class="flex text-center items-center text-text-light pt-4">
      <slot name="author"></slot>
    </div>
  </div>
</template>