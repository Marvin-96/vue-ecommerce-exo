<template>
  <div class="border border-black text-center m-4 p-4">
    Panier : {{ bag.length }}
    <span v-if="numberSelection">article</span>
    <span v-else>articles</span>

    <ul>
      <li v-for="article in bag" :key="article.name">{{ article.name }} | {{ article.price }} €</li>
    </ul>
  </div>
  
</template>

<script>
export default {
  name: "bag-box",
  props: ['bag'],
  computed: {


		},
	

    numberSelection(){
      if(this.bag.length < 2){
        return true
      }
      return false
    }
  }


</script>

<style>

</style>