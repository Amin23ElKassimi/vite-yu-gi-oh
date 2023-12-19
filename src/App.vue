<template lang="">
    <AppHeader/>
    <AppMain/>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import AppMain from './components/AppMain.vue';

export default {
  components:{
    AppHeader,
    CardList,
    AppMain
  },


}
</script>

<style lang="scss">
  @use './styles/general.scss';

</style>