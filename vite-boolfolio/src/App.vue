<script>
//import HelloWorld from './components/HelloWorld.vue'
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default{
    components: [
        AppHeader,
        AppMain
    ],
    components: { AppHeader, AppMain }
}
</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style lang="scss">

  @use './style/general.scss' as *;
</style>
