<template  id="app">
  <div>
    <Display v-on:addName="addNewStud" class="my-2" />
    <Showtable
      @savestudent="saveNewstudent"
      v-bind:Arrays="arrayOfstudent"
      v-on:remove="removeName"
    />
    <!-- <Navbar/
    
    >-->
    <br />
    <br/><br/>
    <br/>
    <br/> <br />
    <br/><br/>
    <br/>
    <br/>
 <br />
    <br/><br/>
    <br/>
    <br/>    <Home/>
    <Cafe/>
    <First v-bind:nameFromApp="name" v-bind:deptFromApp="dept" v-bind:schoolFromApp="school" />
    <Third v-bind:schoolFromApp="school" />

    <br />
    <br />
  </div>
</template>

<script>
import First from "./components/first";
import Third from "./components/third";
// import Navbar from "./components/navbar";
import Home from "./components/home";
import Showtable from "./components/showtable";
import Display from "./components/display";

export default {
  name: "App",
  components: {
    First,
    Third,
    // Navbar,
    Home,
    Showtable,
    Display
  },
  data() {
    return {
      name: "Ken",
      dept: "Software Engineer",
      school: "SQ",
      arrayOfstudent: []
    };
  },
  methods: {
    addNewStud(value) {
      this.arrayOfstudent = [...this.arrayOfstudent, value];
    },
    removeName(objStd) {
      this.arrayOfstudent = this.arrayOfstudent.filter(
        (std, i) => i !== objStd
      );
      console.log(this.arrayOfstudent);
    },
    saveNewstudent(anystudent) {
      this.arrayOfstudent.map(function(arrayOfstudent) {
        if (arrayOfstudent.stdd == anystudent.stdd) {
          //  console.log('hello')
          arrayOfstudent.name = anystudent.name;
          arrayOfstudent.dept = anystudent.dept;
          arrayOfstudent.school = anystudent.school;
        }
      });
    }
  }
};
</script>

<style scoped>
.second {
  background-color: royalblue;
  color: yellow;
}
</style>
