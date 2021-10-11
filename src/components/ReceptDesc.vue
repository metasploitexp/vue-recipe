<template>
    <div v-if="recipe">
        <p><strong>
            <h5> Title: </h5>
             <h4>{{recipe.title}}</h4></strong></p>
        <p> 
            <strong><h5> Description: </h5></strong>
            {{ recipe.desc }} </p>
            <button class="btn remove waves-light red" @click="$emit('remove',recipe.id)">Remove</button>
    </div>
</template>

<script>
export default {
    props: {
       recipe: {
           type: Object
       }
    }
}
</script>

<style scoped>
    div {
        display: block;
        /* position: absolute; */
        /* border: 4px solid black; */
        width: 50%;
        margin-right: 0%;
        margin-top: -75px;
    }
    button {
        margin-top: 20px;
    }
</style>