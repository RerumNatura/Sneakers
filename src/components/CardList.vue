<script setup>
import { inject } from "vue";
import Card from "./Card.vue";

defineProps({
    items:Array,
});

const addToFavorite = inject('addToFavorite');



const onClickAdd = () => {
    alert("Добавлено!")
}
</script>


<template>
    <div class=" grid grid-cols-4 gap-5">
        <Card
            v-for="item in items" 
            :key="item.id"
            :id="item.id"
            :image-url="item.imageUrl"
            :title="item.title"
            :price="item.price"
            :onClickAdd="onClickAdd"
            :onClickFavorite="() => addToFavorite(item)"
            :isFavorite="item.isFavorite"
           />
      </div>
</template>