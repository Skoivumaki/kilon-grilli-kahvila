<script setup lang="ts">
import Button from './ButtonComponent.vue';
import IconCall from './icons/IconCall.vue'

defineProps<{
  variant?: 'text' | 'icons' | 'buttons';
  link?: string;
}>();
</script>

<template>
  <div class="flex flex-col lg:flex-row w-full p-4">
    <div class="h-fit w-full bg-white lg:h-full">
      <div
        class="flex justify-center font-karla text-xl font-bold w-full bg-secondary text-white p-4 gap-2 lg:p-4 lg:text-2xl">
        <i class="flex items-center">
          <slot name="iconHeading"></slot>
        </i>
        <slot name="heading"></slot>
      </div>
      <div class="flex flex-col p-4 items-center justify-center gap-4 lg:flex-row w-full flex-wrap">
        <Button variant="secondary" link="tel:040 3200646">
          <template #iconHeading>
            <IconCall />
          </template>
          <template #heading>040 3200646</template>
        </Button>
        <Button variant="primary">
          <template #iconHeading>
            <IconCall />
          </template>
          <template #heading>Menu</template>
        </Button>
      </div>
    </div>
  </div>
</template>