<template>
  <div class="App">
    <div class="bg"></div>
    <div class="bg bg2"></div>
    <div class="bg bg3"></div>
    <FlashMessage></FlashMessage>
    <v-app-bar app dark>
      <p>Problem 2</p>
    </v-app-bar>
    <v-main>
      <HelloWorld />
    </v-main>
  </div>
</template>
<style scoped>
@import "./App.css";
</style>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },

  data: () => ({
    //
  })
};
</script>
