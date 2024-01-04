
 <!-- HTML & VUEjs -->
<template lang="">
    <div class="mb-3">
        <!-- Select Archetype -->
        <select class="form-select" aria-label="Default select example" @change="selectArchetype(selectedArchetype)" v-model='selectedArchetype'>
            <!-- Popolazione delle Options -->
            <option v-for="(archetype , index) in archetypeList" :key="index" :value="archetype.archetype_name">
                {{archetype.archetype_name}}
            </option>

        </select>
    </div>
</template>

<!-- JavaScript -->
<script>

    // Importa Componente
    import axios from 'axios';

    export default {

        // Variabili da Usare
        data() {
            return {
                archetypeList: [],
                apiUrl: 'https://db.ygoprodeck.com/api/v7/archetypes.php',
                selectedArchetype: '',
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
                        // console.log(this.archetypeList)
                    })
                    .catch(function (error) {
                        // handle error
                        console.log(error);
                    });
            },
            
            selectArchetype(archetype) {
                this.$emit('filter', archetype )
            },      

        },

        // Richiamo delle funzioni in Vue
        created() {
            this.getArchetype();
        },  
            
    }      

</script>

<!-- SCSS -->
<style lang="">
    
</style>






