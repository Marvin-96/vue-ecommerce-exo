<template>
  <title> E-commerce </title> 
  <nav-bar
    @change-component="changeSelectedComponent"
  >
  </nav-bar>
  
  <keep-alive include="product-view">
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @child-event="selectionUpdate"
    >
    </component>
  </keep-alive>
  
</template>

<script>

import ProductView from './components/ProductView.vue' //menu
import Bag from './components/Bag.vue' // Panier
import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    ProductView,
    Bag,
    NavBar
  },
  data() {
    return {
      selectedComponent: 'product-view',
      productSelection: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "bag"){
        return { selection: this.productSelection }
      }
      return false
    },
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    selectionUpdate(value) { 
      this.productSelection.push(value)
    }
  }
}
</script>

<style>
 
</style>
