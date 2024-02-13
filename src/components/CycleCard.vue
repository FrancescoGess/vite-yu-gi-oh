<script>
    
    import {store} from '../store'

    export default{
        name: 'CycleCard',
        props: ['element'],
        data(){
            return{

            }
        }
    }

</script>

<template>

   <div class="col-3">
        <figure class="d-flex flex-column align-items-center gap-3 mb-3">
            <img
            :src="element.card_images[0].image_url_small" 
            :alt="element.name"> 
            <h3>
                {{ element.name }}
                <span>
                    {{ element.archetype }}
                </span>
            </h3>
        </figure>

    </div>

</template>


<style lang="scss" scoped>

    .col-3{
        figure{
            text-align: center;

            img{
                width: 250px;
                height: 300px;
            }
        }

        h3{
            margin: 0;
            font-size: 2rem;
        }
    }

</style>