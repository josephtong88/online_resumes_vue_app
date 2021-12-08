<template>
  <div class="Resume">
    <h1>{{ message }}</h1>
    <div v-for="student in students" v-bind:key="student.id">
      <p><img v-bind:src="student.photo" class="img-thumbnail" alt="profile picture"></p>
      <div class="container-fluid">
        <div class="row">
          <div class="col-12 col-sm-4 text-center">
            <h2>{{ student.first_name }} {{ student.last_name }}</h2>
          </div>
          <div class="col-6 col-sm-4 text-center">
            <h1>2</h1>
          </div>
          <div class="col-6 col-sm-4 text-center">
            <h1>3</h1>
          </div>
        </div>
      </div>
        <p><b>Email:</b> {{ student.email }}</p>
        <p><b>Cell:</b> {{ student.phone_number }}</p>
        <p><b>About Me:</b> {{ student.bio }}</p>
        <p><b>LinkedIn:</b> {{ student.linkedin_url }}</p>
        <p><b>Twitter:</b> {{ student.twitter_handle }}</p>
        <p><b>Website:</b> {{ student.website_url }}</p>
        <p><b>Resume:</b> {{ student.resume_url }}</p>
        <p><b>Github:</b> {{ student.github_url }}</p>
    <div v-for="experience in experiences" v-bind:key="experience.id">
      <p>Start Date: {{ experience.start_date }}</p>
      <p>End Date: {{ experience.end_date }}</p>
      <p>Job Title: {{ experience.job_title }}</p>
      <p>Company Name: {{ experience.company_name }}</p>
      <p>Details: {{ experience.details }}</p>
    </div>
  </div>
  </div>
  </template>

<style>
#contactinfo {
  text-align: left;
  padding-left: 100px;
}
.name {
  font-weight: 400;
}
#resume {
  columns: 2 auto;
}
</style>

<script>
import axios from "axios";
  export default {
    data: function () {
      return {
        message: "Vue my Resume!",
        students: {},
        experiences: {},
      };
    },
    created: function () {
      this.indexStudents();
      this.indexExperiences();
    },
    methods: {
      indexStudents: function () {
        console.log("View student details");
        axios.get("http://localhost:3000/students").then((response) => {
          console.log(response.data);
          this.students = response.data;
        });
      },
      indexExperiences: function () {
        console.log("View experiences");
        axios.get("http://localhost:3000/experiences").then((response) => {
          console.log(response.data);
          this.experiences = response.data;
        });
      },
    },
  };
</script>