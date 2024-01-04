 <!-- HTML & VUEjs -->
<template lang="">
    <main>
        <AppSearch  @filter="getCards" />
        <CardList :cards="cardListFiltred"/>
    </main>
</template>


<!-- JavaScript -->
<script>

    // Importa Componente
    import CardList from './CardList.vue';
    import AppSearch from './AppSearch.vue';
    import axios from 'axios';

    export default {

        //Dichiara Componente 
        components :{
        CardList,
        AppSearch,
        },

        // Variabili da Usare
        data() {
                return {
                    cardListFiltred: [],
                    filtredArchetype: [],
                    apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
                }
        }, 

        // Dove Scrivere le Funzioni
        methods: {
            
            // Metodo Axios
            getCards (archetypeFilter = null) {

                // console.log(archetypeFilter);
                const url = (archetypeFilter !== null) ? `${this.apiUrl}&archetype=${archetypeFilter}` : this.apiUrl;

                axios.get(url)
                    .then( (response) => {
                        // handle success
                        this.cardListFiltred = response.data.data
                        // console.log(this.cardListFiltred)
                    })
                    .catch(function (error) {
                        // handle error
                        console.log(error);
                    });
            }         
        }, 

        // Hook 
        created() {

        this.getCards();
        }

    }

</script>

<!-- SCSS -->
<style lang="scss">

// Use 
@use '../styles/partials/variables.scss' as *;
    
    main {
        background-color: $primary-bg;
        padding: 50px;
    }
    
</style>