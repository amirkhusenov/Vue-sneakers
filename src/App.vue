<script setup>
import { onMounted, ref } from 'vue';
import axios from 'axios';


import Drawer from './components/Drawer.vue';
import Header from './components/Header.vue';
import CardList from './components/CardList.vue';

const items = ref([])


</script>
<template>
  <!-- <Drawer /> -->
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-md mt-10">
    <Header/>
    <CardList/>
  </div>
</template>