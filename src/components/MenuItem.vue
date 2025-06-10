<script setup lang="ts">
defineProps<{ id: number; name: string; price: number; ingredients: string }>();
//console.log('MenuItem props:', { id, name, price, ingredients });
</script>

<template>
    <div class="flex flex-col items-center p-2 gap-2 border-2 border-primary rounded-lg w-[399px] h-fit">
        <div class="flex justify-between items-center gap-2 w-[381px] h-[19px]">
            <div class="flex justify-center items-center text-white font-karla text-lg font-medium w-fit h-[19px]">
                {{ id }}. {{ name }}
            </div>
            <div class="flex justify-center items-center text-white font-karla text-lg font-medium w-fit h-[19px]">
                {{ price.toFixed(2) }} €
            </div>
        </div>
        <div class="flex items-center gap-2 px-1 w-[381px]">
            <div class="flex items-center text-white font-karla text-sm font-light w-fit h-fit">
                {{ ingredients }}
            </div>
        </div>
    </div>
</template>
/* Frame 20 */

/* Auto layout */
display: flex;
flex-direction: column;
align-items: center;
padding: 2px 9px 5px;

width: 399px;
height: 64px;

border: 2px solid #FF5900;
border-radius: 10px;

/* Inside auto layout */
flex: none;
order: 0;
flex-grow: 0;
