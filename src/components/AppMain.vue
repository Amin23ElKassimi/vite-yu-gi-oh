 <!-- HTML -->
<template lang="">
    <main>
        <AppSearch  @filter="getCards" />
        <CardList/>
    </main>
</template>

<!-- JavaScript -->
<script>

// Importa Componente
import CardList from './CardList.vue';
import AppSearch from './AppSearch.vue';
import axios from 'axios';
// 
export default {
    //Dichiara Componente 
    components :{
    CardList,
    AppSearch,
    },


    data() {
            return {
                filtredArchetype: [],
                apiUrl: '',
            }
        }, 

            // Dove Scrivere le Funzioni
    methods: {
        
        // Metodo Axios
        getCards (archetypeFilter = null) {

            console.log(archetypeFilter);
            // const url = (archetypeFilter !== null) ? `${this.apiUrl}&archetype=${archetypeFilter}` : this.apiUrl;

            // axios.get(url)
            //     .then( (response) => {
            //         // handle success
            //         this.archetypeList = response.data
            //         console.log(this.archetypeList)
            //     })
            //     .catch(function (error) {
            //         // handle error
            //         console.log(error);
            //     });
        }         
     },


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