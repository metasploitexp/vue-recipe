<template>
  <AddRecept :onAdd="addRecipe"/>
  <ReceptList :recipes="recipes" @select="selectRecipe"/>
  <ReceptDesc :recipe="current" @remove="removeRecipe"/>
</template>

<script>


import AddRecept from './components/AddRecept.vue'
import ReceptList from './components/ReceptList.vue'
import ReceptDesc from './components/ReceptDesc.vue'

export default {
  components: {
    AddRecept,
    ReceptList,
    ReceptDesc
  },
  data() {
    return {
      recipes: [],
      current: null
    }
  },
  methods: {
    addRecipe(recipe) {
      this.recipes.push(recipe)
    },
    selectRecipe(id) {
      this.current = this.recipes.find(r => r.id === id)
    },
    removeRecipe(id) {
      this.current = null
      this.recipes = this.recipes.filter(r => r.id !== id)
    }
  }
}
</script>

    
<style>
@import "~materialize-css/dist/css/materialize.min.css";
 *{
   position: relative;
   margin: 0 auto;
   padding: 0;
 }
</style>
