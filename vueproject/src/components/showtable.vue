<template>
  <div class="container">
    <!-- <div class="row"> -->
    <!--<div :key="i.studId" v-for="i in Arrays">
                    <div class="m-1">
                        {{i.dept}}
                    </div>    
    </div>-->
    <div class="card p-0 shadow-sm">
      <div class="card-body">
        <div class="card-header card-md-8">
          <h1 class="card-text text-center">
            <i>Student Table</i>
          </h1>
        </div>
        <table class="table table-sm table-bordered table-hover rounded border-secondary">
          <thead>
            <tr>
              <th>S/N</th>
              <th>Name</th>
              <th>Deptment</th>
              <th>School</th>
              <th>Remove</th>
              <th>Edit</th>
            </tr>
          </thead>
          <tbody>
            <tr :key="i.stdd" v-for="(std, i) in Arrays">
              <td>{{std.stdd}}</td>
              <td>{{std.name}}</td>
              <td>{{std.dept}}</td>
              <td>{{std.school}}</td>
              <td>
                <button v-on:click="$emit('remove',i)" class="btn fas fa-remove btn-sm mr-1"></button>
              </td>
              <td>
                <button
                  v-on:click="editme(std)"
                  class="btn btn-danger btn-sm"
                  data-toggle="modal"
                  data-target="#myModal"
                >Edit</button>

                <div class="row">
                  <div
                    class="modal fade col-md-12"
                    id="myModal"
                    role="dialog"
                    data-backdrop="static"
                  >
                    <div class="modal-dialog modal-md">
                      <div class="modal-content">
                        <div class="modal-header">
                          <h4 class="modal-title mx-auto">Edit Here</h4>
                          <button type="button" class="close" data-dismiss="modal">&times;</button>
                        </div>
                        <div class="modal-body">
                          <form action class="m-5">
                            <input
                              type="text"
                              v-model="newstudents.name"
                              class="form-control"
                              placeholder="Name"
                            />
                            <br />
                            <input
                              type="text"
                              v-model="newstudents.dept"
                              class="form-control"
                              placeholder="Depertment"
                            />
                            <br />
                            <input
                              type="text"
                              v-model="newstudents.school"
                              class="form-control"
                              placeholder="School"
                            />
                            <br />
                            <button
                              data-dismiss="modal"
                              @click="saveedit(newstudents)"
                              class="btn btn-sm btn-primary form-control"
                            >Ok</button>
                          </form>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Showtable",
  props: ["Arrays"],
  data() {
    return {
      newstudents: {}
    };
  },
  methods: {
    editme(stdevent) {
      let { stdd, name, dept, school } = stdevent;
      this.newstudents = { stdd, name, dept, school };
      // this.newstudents = s;
      // console.log(s);
    },
    saveedit(getthearr) {
      this.newstudents = getthearr;
      console.log(getthearr);

      this.$emit("savestudent", getthearr);
    }
  }
};
</script>