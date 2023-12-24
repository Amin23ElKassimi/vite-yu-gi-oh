

<!-- HTML -->
<template lang="">
    <AppHeader/>
    <AppMain/>
</template>

<!-- JavaScript -->
<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {

  components :{
    AppHeader,
    AppMain

  }
  
}

</script>


<!-- SASS -->
<style lang="scss">
  @use './styles/general.scss' as *;

</style>