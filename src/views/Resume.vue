<template>
  <div class="Resume">
    <h1>{{ message }}</h1>
    <div v-for="student in students" v-bind:key="student.id">
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
      <p>{{ student.photo }}</p>
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
      };
    },
    created: function () {
      this.indexStudents();
    },
    methods: {
      indexStudents: function () {
        console.log("View all information");
        axios.get("http://localhost:3000/students").then((response) => {
          console.log(response.data);
          this.students = response.data;
        });
      },
    },
  };
</script>