<template>
    <div>
        
        <div v-for="book in books" v-bind:key="book.bookid">
            <!-- BookItem -->
            <BookItem v-bind:book="book" @addBookItem="AddtoCart"/>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
//import BookItem
import BookItem from '@/components/BookItem.vue'


// props, emit
const props =defineProps(['books'])
//const books =ref(props.books)
const emit = defineEmits(['addBook'])

// AddToCart
function AddtoCart(book){
    emit('addBook',book)
}


</script>

<style  scoped>

</style>