<template>
  <div>
    <h1 class="font-sans text-xl text-center mb-6">Lista de produtos</h1>

    <div class="w-full pb-6 grid gap-4 grid-cols-3"> 
      <div v-for="product in cart" :key="product.id" class="relative mt-6 text-gray-700 bg-white shadow-md bg-clip-border rounded-xl w-96">
        <div class="p-6">
          <h5 class="block mb-2 font-sans text-xl antialiased font-semibold leading-snug tracking-normal text-blue-gray-900">
            {{ product.name }}
          </h5>
          <p class="block font-sans text-base antialiased font-light leading-relaxed text-inherit">
            {{ product.description }}
          </p>
          <div class="flex mt-3 justify-end">
            <h5 class="text-2xl font-medium flex flex-1">{{ product.price }}</h5>
            <button @click="removeProduct(product.id)" class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded cursor-pointer">
              remover do carrinho
            </button>
          </div>
        </div>
      </div>   
    </div>
    <div v-if="cart.length">
      <h1 class="font-bold">R$ {{ total.toFixed(2).replace('.', ',') }}</h1>
    </div>
  </div>
</template>
<script setup>
import { onMounted } from 'vue';
import { useCart } from '../composibles/useCart';

const { cart, removeProduct, total, sumTotal } = useCart();

onMounted(() => {
  sumTotal();
})
</script>