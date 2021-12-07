<template>
  <div class="home">
    <h1>{{ message }}</h1>

<p> <TwitterFeed src="https://twitter.com/jack?ref_src=twsrc%5Etfw"></TwitterFeed>
</p>

  </div>
</template>

<style></style>

<script>
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
    };
  },
  created: function () {},
  methods: {},
};
</script>
