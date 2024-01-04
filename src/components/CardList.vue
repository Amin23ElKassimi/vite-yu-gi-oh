<!-- HTML -->
<template lang="">
    <section id="card-list" class="container"> 
        <!-- Nuimero di Carte Trovate -->
        <div class="row">
            <h2>
               Card Trovate{{cards.length}}
            </h2>
        </div>
        <!-- Popolazione Cards -->
        <div class="cards row">
            <SingleCard v-for="card in cards" :key="card.id" :card="card" @click="print()"/>
        </div>

    </section>
</template>

<!-- JAvaScript -->
<script>
    // Importa Componente
    import SingleCard from './SingleCard.vue';
    import axios from 'axios';

    export default {

        // Props provenienti dal padre
        props: {
            cards : {
                type : Array,
                require: true,
            }
        },

        // Variabili da Usare
        data() {
            return {
            }
        },

        // Dichiarare i componenti importati
        components: {
            SingleCard,
        },
        
        // Dove Scrivere le Funzioni
        methods: {  
            // Test Props
            print() {
                console.log(this.cards)
            }
            
        },
        
        // Hook
        created() {
           

        }

    }

</script>

<!-- SCSS -->
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