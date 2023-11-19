<template>
    <div>
        <div v-if="props.cart.length>0" v-bind:key="book.bookid" v-for="book in props.cart">
            <!-- CartItem --> 
            <CartItem :book="book" @increCartItem="Increase" @decreaseCartItem="Decrease" @removeCartItem="Remove"/>
        </div>
        <div v-else>
            <div class="cart-empty" >
                <img src="@/assets/empty.png" style="height: 130px;" alt="" srcset="">
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
//import CartItem
import CartItem from '@/components/CartItem.vue'

// props, emit
const props = defineProps(['cart'])
const emit = defineEmits(['increCart', 'decreaseCart', 'removeCart'])
// Increase
function Increase(bookId){
    emit('increCart',bookId)
}


// Decrease
function Decrease(bookId){
    emit('decreaseCart', bookId)
}



// Remove
function Remove(bookId) {
  emit('removeCart', bookId)
}


</script>

<style  scoped>

</style>