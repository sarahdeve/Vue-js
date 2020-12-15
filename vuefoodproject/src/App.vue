<template>
  <div id="App" >
  
    <Navbar/>
    <HelloWorld/>
    <!-- <Signup/> -->
    <!-- <router-view></router-view> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Navbar from './components/navbar';
// import Signup from './components/signup';

export default {
  name: 'App',
  components: {
   Navbar,
   HelloWorld
  //  Signup
  }
}
</script>

<style scope>
#app {
  
}
body {
  background-image: url("./assets/imges/img2.jpg");
 /* background-image opacity: 0.3 */
    width: 100%;
    height: auto;
}
</style>
