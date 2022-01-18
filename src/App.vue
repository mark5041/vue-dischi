<template>
  <div id="app">
    <Header v-show="!loading" />
    <Main v-show="!loading" />
    <Loader v-show="loading" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Loader from './components/Loader.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Loader
  },
  data() {
      return {
          loading: true,
      }
  },
  mounted() {
      setTimeout(() => {
          this.loading = false;
      }, 2000)
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import "./assets/scss/style.scss";

</style>
