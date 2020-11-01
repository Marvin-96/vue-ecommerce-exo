<template>

  
  <div class="flex">
    <div class="w-1/5">
      <bag-box
        :bag="bag"
      >
      </bag-box>
    </div>
    

    <div class="w-4/5 mt-2">
      <product-card 
        v-for="(product, index) in team.products"
        :key="index"
        :product="product"
        @add-product="addProductToBag"
        >
      </product-card>
    </div>
    

  </div>
    
</template>

<script>
import teamData from '../data/products.json'
import ProductCard from './ProductCard.vue'
import BagBox from './BagBox.vue'

export default {
  name: "product-view",
  components: {
    ProductCard,
    BagBox
  },
  data() {
    return {
      team: teamData,
      bag: []
    }
  },
  methods: {
    addProductToBag(product){
      this.bag.push(product)
      this.$emit('child-event', product)
    }
  }
}
</script>

<style scoped>

</style>