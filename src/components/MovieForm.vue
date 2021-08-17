<template>
    <form @submit.prevent="onSubmit" class="text-center">
        <input 
            class="form-control mb-2"
            placeholder="Enter your Movie name."
            name="name"
            v-model="name"
            type="text">
        <input 
            class="form-control mb-2"
            placeholder="Enter Movie URL."
            name="url"
            v-model="url"
            type="text">
        <button 
            type="submit"
            class="btn btn-info btn-block">
            Add Movie
        </button>
    </form>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
    name: "Form",
    props: {
        addMovie: Function,
    },
    data(){
        return {
            name: "",
            url: ""
        }
    },
    methods: {
        onSubmit: function(){
            this.addMovie({
                name: this.name,
                url: this.url,
                id: uuidv4(),
                date: Date.now()
            });

            this.name = "";
            this.url = "";
        }
    }
}
</script>

<style>

</style>