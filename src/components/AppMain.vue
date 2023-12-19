<!-- HTML -->
<template lang="">
    <main>
        <CardList/>
    </main>
</template>

<!-- JavaScript -->
<script>

import CardList from './CardList.vue';


export default {




    components :{
    CardList,
    },



}
</script>

<!-- SCSS -->
<style lang="scss">
@use '../styles/partials/variables.scss' as *;
    
    main {
        background-color: $primary-bg;
        padding: 50px;
    }
    
</style>