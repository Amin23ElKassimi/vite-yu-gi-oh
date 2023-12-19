<template lang="">
    <section id='Cards' class="container">
        <!-- <article></article> -->
        <div class="row">
            <article v-for="Card in store.CardList" :key="Card.id" class="col-6 col-md-3 col-lg-2 mb-5">
                <SingleCard :Card="Card" />
            </article>
        </div>
    </section>
</template>

<script>
import axios from 'axios';
import { store } from '../js/store.js';
import SingleCard from './SingleCard.vue';

export default {
    
    data() {
        return {
            store,
        }
    },

    components:{
        SingleCard
    },
}
</script>

<style lang="scss">

</style>