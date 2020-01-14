<template>
  <div id="app">
    <img alt="Minyi minyi gan!" style="heigh: 350px; width: 300px" src="./assets/minyi.jpeg" />
    <MinyiComponent msg="Hinyi Iring2 spiciil ying bisi dingir!" />
    <FooterComponent />
  </div>
</template>

<script>
import MinyiComponent from "./components/MinyiComponent.vue";
import FooterComponent from "./components/Footer.vue";

export default {
  name: "app",
  components: {
    MinyiComponent,
    FooterComponent
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 100vw;
}
</style>
