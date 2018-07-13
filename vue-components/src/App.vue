<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <HelloWorld msg="Hellotest"/> -->
    <!-- <SwitchButton v-model="lightOn"/>
    <h1>{{lightOn}}</h1> -->
    <CountryNames/>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
//import SwitchButton from "./components/SwitchButton.vue";
// import ck from "./components/Counter.vue";
import CountryNames from "./components/CountryNames.vue";
export default {
  name: "app",
  components: {
    // HelloWorld
    // SwitchButton
    // ck
    CountryNames
  },
  // data(){
  //   return {
  //     lightOn: false,
  //   };
  // },
  // methods:{
  //   setLight(newlight){
  //     this.lightOn = newlight;
  //   },
  // },
};
</script>


