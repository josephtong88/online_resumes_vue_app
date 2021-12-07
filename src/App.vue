<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/resume">Resume</router-link>
    </div>
    <router-view />
    <div class="container">
      <div class="row">
        <div class="col-3">
          <div class="headers">
            Jonathan Miksis
          </div>
        </div>
        <div class="col-9">
          2 of 2
        </div>
      </div>
      <div class="row">
        <div class="col-3">
          <div class="headers">
          Contact
          <hr>
          </div>
        </div>
        <div class="col-9">
          2 of 3
        </div>
      </div>
      <div class="row">
        <div class="col-3">
          <div class="headers">
          <b>Address:</b>
          <br>
          </div>
          200 Quarry Hills Drive
          Quincy, MA 02169
        </div>
        <div class="col-9">
          2 of 3
        </div>
      </div>
      <div class="row">
        <div class="col-3">
          <br>
          <div class="headers">
          <b>Phone:</b>
          </div>
          (603) 812-7478
          <br>
        </div>
        <div class="col-9">
          2 of 3
        </div>
      </div>
      <div class="row">
        <div class="col-3">
          <br>
          <div class="headers">
          <b>Email:</b>
          </div>
          jmiksis13@gmail.com
          <br>
        </div>
        <div class="col-9">
          2 of 3
        </div>
      </div>
</div>

  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.headers {
  font-family: sans-serif, Arial, Helvetica, sans-serif;
  font-weight: 900;
  font-size: 20px;
}
</style>
