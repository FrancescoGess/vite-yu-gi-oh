<script>

import AppHeader from './components/AppHeader.vue';
import LoaderApi from './components/LoaderApi.vue';
import AppSearch from './components/AppSearch.vue';
import CardMain from './components/CardMain.vue';
import { store } from '../src/store';
import axios from 'axios';

export default{
    components: {
    AppHeader,
    LoaderApi,
    AppSearch,
    CardMain
},
    data(){
        return{
            store,
        }
    },
    methods:{
        getCards(){
            this.LoaderApi = true
            if (this.AppSearch !== ""){
                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.formSearch}`).then(res => {
                    store.CycleCard = res.data.data

                    this.LoaderApi = false
                })
            } else {
                axios.get(store.apiUrl).then(res => {
                    store.CycleCard = res.data.data
                    this.LoaderApi = false
                })
            }
        },
    }, mounted(){
        this.getCards()

        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then ((res) => store.archetypes = res.data)
    }
}

</script>

<template>
<AppHeader></AppHeader>
<main>
    <AppSearch @formSearch="getCards"></AppSearch>
    <CardMain></CardMain>
</main>
</template>

<style>

</style>
