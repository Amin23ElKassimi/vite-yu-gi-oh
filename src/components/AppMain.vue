<!-- HTML -->
<template lang="">
    <main>
        <CardList/>
    </main>
</template>

<!-- JavaScript -->
<script>

// Importa Componente
import CardList from './CardList.vue';

// 
export default {
    //Dichiara Componente 
    components :{
    CardList,
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