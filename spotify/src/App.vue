<template>
  <div id="app">
    <Header />
    
    <Main />
  </div>
</template>

<script>

import Main from './components/MainComponent.vue'
import Header from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    Main,
    Header
  }
}
</script>

<style lang="scss">

</style>
