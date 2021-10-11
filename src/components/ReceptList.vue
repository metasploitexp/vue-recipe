<template>
    <div>
        <div v-if="recipes.length">
         <ul class="collection"
         v-for="recipe in recipes" :key="recipe.title"
         @click="$emit('select', recipe.id)"
         >
            <li class="collection-item">{{ recipe.title }}</li>
           
        </ul>
        </div>
        <div v-else><h3> Нет рецептов </h3></div>
    </div>
</template>

<script>
export default {
    props: {
        recipes: {
            type: Array
        }
    },
    data() {
        return {
        
        }
        
    }
}
</script>

<style scoped>
div {
    /* border: 4px solid black; */
    width: 50%;
    margin-left: 0%; 
}
</style>