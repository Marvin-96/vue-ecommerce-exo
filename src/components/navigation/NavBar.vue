<template>
  <div class="bg-blue-300 p-2">
    <a href="#" @click="changeComponent('product-view')"> Nos Produits</a> | 
    <a href="#" @click="changeComponent('bag')"> Mon Paniers</a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  methods: {
    changeComponent(value) {
      this.$emit('change-component', value)
    }
  }
}
</script>

<style>

</style>