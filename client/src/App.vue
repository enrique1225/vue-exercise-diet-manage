<template>
  <div id="app">
    <MyNav></MyNav>
    <router-view/>
  </div>
</template>

<script>
import MyNav from "@/components/Nav.vue";

export default {
  components: {
    MyNav
  }
}
</script>

<style lang="scss">
  @import '../src/assets/scss/fit.scss'
</style>
