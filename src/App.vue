<template>
  <div id="app">
    <h1>JetWay Admin</h1>
    <div class="background">
      <img src="./assets/airplane.svg">
      <HelloWorld msg="JetWay - Admin"/>
    </div>
    
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  }
};
</script>

<style lang='scss' scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
  position: relative;
  width:100%;
  .background {
    position: relative;
    margin-left: auto;
    margin-right: auto;
   width: 800px;
    img {
   width: 800px;
    }
    >div {
      position: absolute;
      top: 0;
      width: 800px;
      height: 473px;
    }
  }
}
</style>
