<template>
    <div>
        <form @submit.prevent="onSubmit">
            <div class="row" id="form">
                <div class="col s12 m6">
                <div class="card deep-purple lighten-2">
                    <div class="card-content white-text">
                    <span class="card-title">Enter your recipe</span>
                    <input :placeholder="titleHolder" type="text" v-model="title">
                    <input :placeholder="descHolder" type="text" v-model="desc">
                    </div>
                    <div class="card-action">
                    <button type="submit" class="waves-effect waves-light btn">Add </button>
                    </div>
                </div>
                </div>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    props: {
        onAdd: {
           type: Function,
            required: true
        }
    },
    data() {
        return {
            titleHolder: 'Enter title',
            descHolder: 'Enter description',
            title: '',
            desc: ''
        }
    },
    methods: {
        onSubmit() {
            const recipe = {
                title: this.title.trim(),
                desc: this. desc.trim(),
                id: Date.now()
            }
            this.title = this.desc = ''
            this.onAdd(recipe)
        }
    }
}
</script>

<style scoped>
    #form {
        /* position: absolute; */
        margin-left: 25%;
        
    }
    #title {
      text-align: center;
    }
</style>