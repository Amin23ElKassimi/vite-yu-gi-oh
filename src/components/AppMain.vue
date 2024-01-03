<!-- HTML -->
<template lang="">
    <main>
        <AppSearch/>
        <CardList/>
    </main>
</template>

<!-- JavaScript -->
<script>

// Importa Componente
import CardList from './CardList.vue';
import AppSearch from './AppSearch.vue';

// 
export default {
    //Dichiara Componente 
    components :{
    CardList,
    AppSearch,
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