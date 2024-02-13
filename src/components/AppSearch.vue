<script>

    import {store} from '../store'

    export default{
        name: "AppSearch",
        emits:['formSearch'],
        data(){
            return{
                store,
            }
        }
    }

</script>

<template>

    <nav class="container d-flex flex-column align-items-center justify-content-center mt-2">
        <div class="d-flex align-items-center justify-content-center mb-3">
            <select
            class=""
            name="filterCards" 
            id="filterCards"
            v-model="store.formSearch">
            <option disabled selected hidden>Select</option>
            <option
            :value="archetype.archetype_name"
            v-for="(archetype, index) in store.archetypes"
            :key="index">{{ archetype.archetype_name }}</option>
            </select>

             <form class="d-flex">
            
                <input 
                class="form-control me-2"
                type="search"
                name="search"
                placeholder="Search cards">
                <button
                class="btn btn-outline-dark"
                type="submit"
                @click.prevent="$emit('formSearch')">Search
                </button>
            </form>
        </div>
    </nav>

    <div class="container border rounded my-5 d-flex alig-items-center justify-content-center">

        <!-- <p>
            Your results: {{ store.CycleCard.length }}
        </p> -->

    </div>
</template>

<style>

    form{
        width: 500px;
    }
</style>