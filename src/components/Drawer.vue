<script setup>
    import CartListItem from './CartListItem.vue';
</script>

<template>
    <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70" ></div>
    <div class="bg-white w-96 h-full fixed right-0 top-0 z-20 p-8">
        <div class="flex items-center gap-5 mb-8">
            <svg class="opacity-30 cursor-pointer rotate-180 hover:opacity-100 transition hover:-translate-x-1" xmlns="http://www.w3.org/2000/svg" width="16" height="14" viewBox="0 0 16 14" fill="none">
                <path d="M1 7H14.7143" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M8.71436 1L14.7144 7L8.71436 13" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
        <h2 class="text-2xl font-bold">Коризна</h2>
        </div>

        <CartListItem/>        

        <div class="flex flex-col gap-5 mt-6 mb-6">
            <div class="flex items-baseline gap-2">
                <span>Итого:</span>
                <div class="flex-1 border-b border-dashed border-gray-300"></div>
                <b>12900 ₽</b>
            </div>
            <div class="flex items-baseline gap-2">
                <span>Налог  5%:</span>
                <div class="flex-1 border-b border-dashed border-gray-300"></div>
                <b>900 ₽</b>
            </div>
        </div>

        <button class="bg-lime-400 w-full rounded-xl py-4 text-white font-bold"> 
            Оформить заказ
        </button>
    </div>
</template>

<style>
    
</style>
