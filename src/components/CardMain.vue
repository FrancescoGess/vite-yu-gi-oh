<script>

    import CycleCard from './CycleCard.vue';
    import {store} from '../store'


    export default {
        name: 'CardMain',
        components:{
            CycleCard
        },
        data() {
            return {
                store,
            }
        },
    }
</script>

<template>

    <div class="container mt-3">
        <div class="row">
            <CycleCard
            v-for="(card, index) in store.CycleCard"
            :key="index"
            :element="card"
            ></CycleCard>
        </div>
    </div>
    
</template>