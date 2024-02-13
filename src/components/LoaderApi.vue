<script>
    import { store } from '../store'

    export default{
        name: 'LoaderApi',
        data(){
            return{
                store,
            }
        }
    }
</script>

<template>
    <div class="load-api d-flex justify-content-center">
        <div class="load">

        </div>
    </div>
</template>

<style lang="scss" scoped>

.load-api{
    height: calc( 100vh - 518px );
    border: 1px solid black;

    load{
        width: 150px;
        height: 150px;
    }
}

</style>