<template>
  <div id="app">
    <Home></Home>
  </div>
</template>

<script lang="ts">
// import { Component, Vue } from "vue-property-decorator";
import { defineComponent } from "vue";
import Home from "@/components/views/Home.vue";

// @Component({
//   components: {
//     Home,
//   },
// })
// export default class App extends Vue {}

export default defineComponent({
  components: {
    Home,
  },
});
</script>

<style lang="stylus">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
