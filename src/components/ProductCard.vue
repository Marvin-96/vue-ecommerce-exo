<template>
  <div 
    class="border m-2 p-2 flex justify-between">
    <div>
      <h1 class="text-lg font-bold">{{ product.name }}</h1>
      <p> {{ product.price }} € </p>
      <p> {{ product.brand }}  </p>
    </div>
    <base-button
      text="Ajouter au Panier"
      @click="addToSelection"
    >
    </base-button>
  </div>    
</template>

<script>
export default {
  name: "product-card",
  props: ['product'],
  methods: {
    addToSelection() {
      this.$emit('add-product', this.product)
    }
  }
}
</script>

<style scoped>

</style>