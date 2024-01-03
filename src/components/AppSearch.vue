

<template lang="">
    <div class="mb-3">
        <!-- Inserire una Select -->
        <select class="form-select" aria-label="Default select example">
            <option selected>Open this select menu</option>
            <option v-for="(archetype , index) in archetypeList" :key="index" :value="archetype.archetype_name">
                {{archetype.archetype_name}}
            </option>
        </select>
    </div>
</template>


<script>

import axios from 'axios';


    export default {

        data() {
            return {
                archetypeList: [],
                apiUrl: 'https://db.ygoprodeck.com/api/v7/archetypes.php',
            }
        }, 

            // Dove Scrivere le Funzioni
    methods: {
        
        // Metodo Axios
        getArchetype() {
            // Make a request for a user with a given ID
            axios.get(this.apiUrl)
                .then( (response) => {
                    // handle success
                    this.archetypeList = response.data
                    console.log(this.archetypeList)
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        }         
     },


     created() {
         
        this.getArchetype();
        
     },  
        
    }      

</script>



<style lang="">
    
</style>






