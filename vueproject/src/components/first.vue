<template>
  <div class="card shadow-sm col-md-6 mx-auto mt-5">
    <h3 class>
      First
      <span class="text-danger">Component</span>
    </h3>
    <p>My name is {{nameFromApp}}, i am a {{deptFromApp}}</p>
    <div class="mt-2">
      <h3>Second Component</h3>
      <Second v-bind:age="age" v-bind:anotherName="schoolFromApp" />
    </div>
    <div v-if="num<0">Num is less than or equal to zero</div>

    <div v-else-if="num<50">Num is less than or equal to 50</div>
    <div v-else-if="num<=100">Num is less than or equal to 100</div>
    <div v-else>Greater than 100</div>
    <div v-if="verify">Display me based on conditions</div>
    <div v-else>Don't show me</div>
    <button v-on:click="addnum">addnum</button>
    <button v-on:click="reducenum">reducenum</button>
    <button v-on:click="verification">Verify</button>
    {{num}}
    <div v-bind:class="{'bg-success':num >=50, 'bg-danger':num<50}">{{num}}</div>

    <div v-bind:style="myStyle">{{num}}</div>

    <div v-bind:style="{'background-color':bg, color:'white', 'font-size':`${font}px`}">good {{num}}</div>
    <button v-on:click="verification">Verify</button>
    <button v-on:click="increaseFont">font</button>
    <!-- <div :bind:style="randomColor">very good</div>
    <div class="bg-success">excellent</div>
    <div id="sefemi">a very pretty girl</div>
    <div class="second">the second div</div>-->
  </div>
</template>
<script>
import Second from "./second";
export default {
  name: "First",
  props: ["nameFromApp", "schoolFromApp", "deptFromApp"],
  components: {
    Second
  },
  data() {
    return {
      num: 0,
      age: 100,
      verify: true,
      myStyle: {
        backgroundColor: "red",
        color: "yellow"
      },
      Mycolor: "purple",
      bg: "blue",
      font: 2
    };
  },
  methods: {
    verification() {
      this.verify = !this.verify;
    },
    addnum() {
      this.num = this.num + 10;
    },
    reducenum() {
      this.num = this.num - 15;
    },
    myFunc() {
      return {
        color: "dodgerblue",
        "background-color": "pink"
      };
    },
    // randomNum() {
    //    return Math.floor(Math.random()*1000000);
    //  },
    // randomColor() {
    // this.bg = `#${this.randomNum()}`;
    // }
    randomColor() {
      let myNum = Math.floor(Math.random() * 1000000);
      this.bg = `#${myNum}`;
    },
    increaseFont() {
      this.font += 2;
    }
  }
};
</script>
<style scoped>
#sefemi {
  background-color: aquamarine;
  color: red;
}
.second {
  background-color: purple;
  color: yellow;
}
</style>