<template>
    <header class="flex justify-center items-center max-w-full p-6 lg:px-8 bg-white">
        <nav class="w-full flex justify-center" aria-label="Global">
            <div class="grid gap-4 grid-cols-2 text-md font-semibold leading-6 text-gray-900">
                <router-link to="products" class="hover:text-purple-500">Produtos</router-link>
                <router-link to="cart" class="hover:text-purple-500">Carrinho</router-link>
            </div>
        </nav>
    </header>
</template>

<script setup>
</script>