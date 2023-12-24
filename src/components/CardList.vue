<!-- HTML -->
<template lang="">
    <section id="card-list" class="container"> 
        <div class="row">
            <h2>
               Card Trovate{{cardList.length}}
            </h2>
        </div>

        <div class="cards row">
            <SingleCard v-for="card in cardList" :key="card.id" :card="card" />
        </div>

    </section>
</template>

<!-- JAvaScript -->
<script>
import SingleCard from './SingleCard.vue';
import axios from 'axios';

export default {

    // Variabili da Usare
    data() {
        return {
            cardList: [],
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
            
        }
    },
    // DDichiarare i componenti importati
    components: {
        SingleCard,
        

    },
    // Dove Scrivere le Funzioni
    methods: {
        
        // Metodo Axios
        getcards() {
            // Make a request for a user with a given ID
            axios.get(this.apiUrl)
                .then( (response) => {
                    // handle success
                    console.log(response);
                    this.cardList = response.data.data
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }       
    },
    
    // Hook
    created() {

        this.getcards();

    }

}

</script>


<!-- SASS -->
<style lang="scss">
@use '../styles/partials/variables.scss' as *; 

    #card-list{
        background-color: white;
    }

    .row{
        color: white;
    }

    h2 {
        background-color: $dark-bg;
    }
    
</style>