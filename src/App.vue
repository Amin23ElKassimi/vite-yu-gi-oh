<template lang="">
  <AppHeader/>
  <main>
    <AppSearch/>
    <CardList/>
  </main>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import AppSearch from './components/AppSearch.vue';

export default {
  components:{
    AppHeader,
    CardList,
    AppSearch
  },


}
</script>

<style lang="scss">
  @use './styles/general.scss';

</style>