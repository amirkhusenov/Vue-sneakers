<script setup>
    import { reactive } from 'vue';

    const nav = reactive([
        {
            img: "/cart.svg", 
            text: "1205 руб."
        },
        {
            img: "/heart.svg", 
            text: "Закладки"
        },
        {
            img: "/profile.svg", 
            text: "Профиль"
        },
    ])
</script>

<template>
    <header class="flex justify-between border-b border-slate-100 px-10 py-8">
        <div class="flex items-center gap-4">
            <img class="w-10" src="/logo.png" alt="Logo">
            <div>
                <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
                <p class="text-slate-500">Магазин лучших кроссовок</p>
            </div>
        </div>
        <ul class="flex items-center gap-10">
            <li class="flex items-center gap-2 text-gray-500 hover:text-gray-600 cursor-pointer" v-for="item in nav" :key="item">
                <img :src="item.img" alt="">
                <span>{{ item.text }}</span>
            </li>
        </ul>
    </header>
</template>

<style>
    
</style>