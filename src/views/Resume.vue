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
    <div v-for="education in educations" v-bind:key="education.id">
      <p>Start Date: {{ education.start_date }}</p>
      <p>End Date: {{ education.end_date }}</p>
      <p>Degree: {{ education.degree }}</p>
      <p>University Name: {{ education.university_name }}</p>
      <p>Details: {{ education.details }}</p>
    </div>
    <div v-for="skill in skills" v-bind:key="skill.id">
      <p>{{ skill.skill_name }}</p>
    </div>
    <div v-for="capstone in capstones" v-bind:key="capstone.id">
      <p>{{ capstone.name }}</p>
      <p>{{ capstone.description }}</p>
      <p>{{ capstone.url }}</p>
      <p>{{ capstone.screenshot }}</p>
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
        educations: {},
        skills: {},
        capstones: {}
      };
    },
    created: function () {
      this.indexStudents();
      this.indexExperiences();
      this.indexEducations();
      this.indexSkills();
      this.indexCapstones();
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
      indexEducation: function () {
        console.log("View education");
        axios.get("http://localhost:3000/educations").then((response) => {
          console.log(response.data);
          this.educataions = response.data;
        });
      },
      indexSkills: function () {
        console.log("View Skills");
        axios.get("http://localhost:3000/Skills").then((response) => {
          console.log(response.data);
          this.skills = response.data;
        });
      },
      indexCapstone: function () {
        console.log("View Capstone");
        axios.get("http://localhost:3000/capstones").then(
          (response) => {
            console.log(response.data);
            this.capstones = response.data;
        });
      },
    },
  };
</script>