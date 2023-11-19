<template>
    <div class="book-item" >
    
        <h2>{{ book.title }}</h2>
        <div class="book-detail">
            <img v-bind:src="book.thumbnailUrl"/><br />
            <b>Price:</b> {{ book.price }}<br />
            <b>Author:</b> {{ book.author }}<br />
            <b>Category:</b> {{ book.category }}<br />
            <b>ISBN:</b> {{ book.isbn }}<br />
            <b>Pages:</b> {{ book.pageCount }}<br />
            <b>Description:</b>
            <p>{{ book.shortDescription }}</p>
            <div class="container-fluid m-0 p-0">
                <div class="row justify-content-around">
                    <div class="col">
                        <button style="margin-top: 1rem;" class="btn btn-primary" @click="AddToCart(book.bookid,book.title,book.price)">Add to Cart</button>
                    </div>
                    <div class="col" style="text-align: right;margin-top: 1.5rem;">
                        <a href="#top" style="text-decoration:none;">
                            <i class="bi bi-arrow-up-circle"></i> Back to Top
                        </a>
                    </div>
                </div>
            </div>
         
            <br />
        </div>
      
    </div>
</template>

<script setup>
import { ref } from 'vue'

// props, emit
const props = defineProps(['book'])
const book=ref(props.book)
const emit = defineEmits(['addBookItem'])
// AddToCart
function AddToCart(bookId,bookTitle,bookPrice){
    emit('addBookItem',{"bookid":bookId,"title":bookTitle,"price":bookPrice});
}
</script>

<style scoped>


</style>