<template>
  <div>
    <h1 class="font-sans text-xl text-center mb-6">Lista de produtos</h1>

    <div class="w-full pb-6 grid gap-4 grid-cols-3"> 
      <div v-for="product in products" :key="product.id" class="relative mt-6 text-gray-700 bg-white shadow-md bg-clip-border rounded-xl w-96">
        <div class="p-6">
          <h5 class="block mb-2 font-sans text-xl antialiased font-semibold leading-snug tracking-normal text-blue-gray-900">
            {{ product.name }}
          </h5>
          <p class="block font-sans text-base antialiased font-light leading-relaxed text-inherit">
            {{ product.description }}
          </p>
          <div class="flex mt-3 justify-end">
            <h5 class="text-2xl font-medium flex flex-1">{{ product.price }}</h5>
            <button @click="addProduct(product)" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded cursor-pointer">
              <Icon icon="ic:outline-shopping-cart" />
            </button>
          </div>
        </div>
      </div> 
    </div>
  </div>
</template>

<script setup>
import { useCart } from '../composibles/useCart';
import { Icon } from '@iconify/vue';

const { products, addProduct } = useCart();
</script>
