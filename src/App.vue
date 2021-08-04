<template>
  <!-- bootstrap include for icon-->
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.5.0/font/bootstrap-icons.css"
  />
  <div id="app">
    <main>
      <div class="header-wrap">
        <div class="header" @click="goAbout">
          Lang VUE <i class="bi bi-translate"></i>
        </div>
      </div>

      <div class="search-box" v-if="aboutToggle === false">
        <select name="input-lang" id="input-lang" class="search-bar">
          <option value="eng">English</option>
          <option value="sr">Serbian</option>
          <option value="esp">Spanish</option>
        </select>
        <select name="input-lang" id="output-lang" class="search-bar">
          <option value="eng">English</option>
          <option value="sr">Serbian</option>
          <option value="esp">Spanish</option>
        </select>
      </div>

      <div class="about-wrap" v-if="aboutToggle === true">
        <div class="about">
          <p class="about-title">About Lang VUE</p>
          <p class="about-body">
            Lang VUE was developed in Vue.js. This is my second application that
            I made using Vue.js.
          </p>
          <p class="about-body about-foot">
            Lang VUE combines my love for programming with my interest in
            learning new languages. It uses the Google Translate API, where the
            app sends requests and displays the result.
          </p>
          <p class="about-body about-foot">
            For more of my projects, visit my
            <a target="_blank" href="https://github.com/nemanjaone">GitHub</a>.
          </p>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      //Data
      query1: "",
      query2: "",
      aboutToggle: false,
    };
  },
  methods: {
    goAbout() {
      let aboutToggle = this.aboutToggle;
      if (aboutToggle === false) {
        this.aboutToggle = true;
        this.weather.main = undefined;
      } else {
        this.aboutToggle = false;
        this.query = "";
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: "montserrat", sans-serif;
}
#app {
  background-image: url("https://images.pexels.com/photos/942872/pexels-photo-942872.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260");
  transition: 1s;
  background-size: cover;
  background-position: right;
  transition: 0.4s;
  min-height: 100vh;
}
main {
  min-height: 100vh;
  padding: 25px;
  background-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.25),
    rgba(0, 0, 0, 0.75)
  );
}
.header-wrap {
  display: flex;
}
.header {
  margin-left: auto;
  font-size: 25px;
  font-weight: 300;
  color: #fff;
  margin-bottom: 25px;
  border-radius: 0px 16px;
  padding: 10px;
  font-family: "Bebas Neue", sans-serif;
  text-shadow: 2px 3px rgba(0, 0, 0, 1);
}
.header:hover {
  cursor: pointer;
}
.about-wrap {
  width: 100%;
  max-width: 700px;
  margin-bottom: 30px;
  margin-left: auto;
  margin-right: auto;
}
.about-wrap .about {
  display: block;
  width: 100%;
  padding: 15px;
  color: #313131;
  font-size: 20px;
  appearance: none;
  border: none;
  outline: none;
  background: none;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.8);
  border-radius: 16px;
  transition: 0.4s;
}
.about-title {
  font-weight: 550;
  text-align: center;
  margin-top: 5px;
  margin-bottom: 15px;
}
.about-body {
  margin-left: 5px;
  margin-right: 5px;
}
.about-list {
  margin-left: 40px;
  margin-top: 10px;
}
.about-foot {
  margin-top: 10px;
}
.search-box {
  width: 100%;
  max-width: 700px;
  margin-bottom: 30px;
  margin-left: auto;
  margin-right: auto;
}
.search-box .search-bar {
  display: inline-block;
  width: 45%;
  padding: 15px;
  margin-left: 10px;
  margin-right: 10px;
  color: #313131;
  font-size: 20px;
  appearance: none;
  border: none;
  outline: none;
  background: none;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  transition: 0.4s;
}
.search-box .search-bar:focus {
  box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
}
</style>
