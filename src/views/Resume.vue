<template>
  <div class="Resume">
    <h1>{{ message }}</h1>
    <div v-for="student in students" v-bind:key="student.id">
      <p><img v-bind:src="student.photo" class="img-thumbnail" alt="profile picture"></p>
      <h2>{{ student.first_name }}</h2>
      <h2> {{ student.last_name }}</h2>
      <p>{{ student.email }}</p>
      <p>{{ student.phone_number }}</p>
      <p>{{ student.bio }}</p>
      <p>{{ student.linkedin_url }}</p>
      <p>{{ student.twitter_handle }}</p>
      <p>{{ student.website_url }}</p>
      <p>{{ student.resume_url }}</p>
      <p>{{ student.github_url }}</p>
    </div>
    <div v-for="experience in experiences" v-bind:key="experience.id">
      <p>Start Date: {{ experience.start_date }}</p>
      <p>End Date: {{ experience.end_date }}</p>
      <p>Job Title: {{ experience.job_title }}</p>
      <p>Company Name: {{ experience.company_name }}</p>
      <p>Details: {{ experience.details }}</p>
    </div>
  </div>
</template>

<style></style>

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