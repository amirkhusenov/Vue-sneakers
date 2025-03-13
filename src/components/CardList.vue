    <script setup>
    import { onMounted, reactive, ref, watch } from 'vue';
    import axios from 'axios';
    import Card from './Card.vue';

    const items = ref([])    

    const filters = reactive({
        sortBy: 'title',
        searchQuery: ''
    })

    const fetchFavorites = async () => {
        try {
            const { data } = await axios.get(`https://4ee97867e9aaf312.mokky.dev/favorites`)

            items.value = data 
        } catch (err) {
            console.log(err)
        }
    }

    const onChangeSelect = (event) => {
        filters.sortBy = event.target.value
    }


    const onChangeSearchInput = (event) => {
        filters.searchQuery = event.target.value
    }

    const fetchItems = async () => {
        try {
            const params = {
                sortBy: filters.sortBy,
            }

            if (filters.searchQuery) {
                params.title =  `*${filters.searchQuery}*`
            }
            const { data } = await axios.get(`https://4ee97867e9aaf312.mokky.dev/sneakers`, {
                params
            })
            items.value = data;
        } catch (err) {
            console.log(err)
        }
    }
    onMounted(fetchItems)
    watch(filters, fetchItems)
</script>

<template>
    <div class="m-10">
    <div class="flex justify-between items-center">
        <h2 class="font-bold text-3xl mb-8">Все кроссовки</h2>
        <div class="flex gap-4">
            <select @change="onChangeSelect" class="py-2 px-3 border border-gray-200 rounded-md outline-none">
                <option value="name">По названию</option>
                <option value="price">По цене (дешевые)</option>
                <option value="-price">По цене (дорогие)</option>
            </select>
            <div class="relative"> 
                <img class="absolute left-3 top-3" src="/search.svg">
                <input @input="onChangeSearchInput" class="outline-none border border-gray-200 rounded-md py-2 pl-11" type="text" placeholder="Поиск...">
            </div>
        </div>
    </div>
    
    <div class="grid grid-cols-4 gap-4">
        <Card 
            v-for="item in items" 
            :key="item.id"
            :title="item.title"
            :img ="item.imageUrl"
            :price="item.price"
            :onClickAdd="item.onClickAdd"              
        />
    </div>
    </div>
</template>

<style>
    
</style>