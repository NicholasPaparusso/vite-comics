<script>
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';
  import AppMenu from './components/AppMenu.vue';
  import AppFooter from './components/AppFooter.vue';

  export default {
  name: 'App',
  components:{
    AppHeader,
    AppMain,
    AppMenu,
    AppFooter,
  }
  }
</script>

<template>

  <AppHeader/>
  <AppMain/>
  <AppMenu/>
  <AppFooter/>

</template>


<style lang="scss">

 @use './styles/general.scss'
 
</style>