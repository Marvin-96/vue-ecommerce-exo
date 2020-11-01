<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Mon Panier</h1>

    <div v-if="bag.length == 0">
      <p>Aucun article sélectionné</p>
    </div>
    <div v-else>
      <div
        v-for="product in bag"
        :key="product.name" 
        class="border border-black my-4 p-2"
      >
        <h1 class="text-5xl">{{ product.name }} </h1>
        <span> marque : {{ product.brand }}</span>
        <img :src="require('../assets/img/' + product.photo)" alt="">
        <span> Prix : {{ product.price }}</span>
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "bag",
  props: ['bag'],
}
</script>

<style>

</style>