<template>
    <div class="cart-item" >
    
        <b>{{book.title}}</b><br />
        <b>Price:</b> {{book.price}} ฿<br />
        <b>Qty:</b> {{book.qty}}<br />
        <div align="center" style="margin-top: 1rem;">
            <button class="btn btn-success" @click="Increase(book.bookid)"><i class="bi bi-plus"></i></button>&nbsp;
            <button class="btn btn-info" @click="Decrease(book.bookid)"><i class="bi bi-dash"></i></button>&nbsp;
            <button class="btn btn-danger" @click="Remove(book.bookid)"><i class="bi bi-trash-fill"></i></button>
        </div>
    
    </div>
</template>

<script setup>
import { ref } from 'vue'

// props, emit
const props = defineProps(['book'])
const emit = defineEmits(['increCartItem', 'decreaseCartItem', 'removeCartItem'])

// Increase
function Increase(bookId){
    emit('increCartItem',bookId)
}


// Decrease
function Decrease(bookId){
    emit('decreaseCartItem', bookId)
}



// Remove
function Remove(bookId) {
  emit('removeCartItem', bookId)
}
</script>

<style  scoped>

</style>