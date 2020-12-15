<template>
  <div class="container">
    <div class="row">
      <!-- <form class="col-md-4 form-horizontal"> -->
      <div class="form-group form-hrizontal">
        <input v-model="stdname" type="text" class="form-control mb-2" placeholder="Name" />
        <input v-model="stddept" type="text" class="form-control mb-2" placeholder="Department" />
        <input v-model="stdschool" type="text" class="form-control mb-2" placeholder="School" />
        <button v-on:click="addStdName" class="btn btn-sm btn-success">Add</button>
      </div>
    
        <div>
        
        </div>
      <!-- </form> -->
    </div>
  </div>
</template>
<script>
let  Studid = 1;
export default {
  name: "Display",
  data() {
    return {
      stdname: "",
      stddept: "",
      stdschool: ""
    };
  },
  methods: {
    addStdName() {
      const objStd={
        stdd: Studid++,
        name:this.stdname,
        dept:this.stddept,
        school: this.stdschool
      }
      console.log(objStd);
      this.$emit("addName",objStd);
    }
  }
  // methods: {
  //     addName(e) {
  //         let object = {
  //             studId: Studid++,
  //             name: this.stdname,
  //             dept: this.stddept,
  //             school: this.stdschool
  //         };
  //         e.preventDefault();
  //         this.$emit("addthename", object);
  //         // alert(name)
  //     },

  // }
};
</script>