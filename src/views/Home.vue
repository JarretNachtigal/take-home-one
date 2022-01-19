<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h1>Github Watcher Take Home</h1>
    <h2>Frameworks:</h2>
    <h3>Vue</h3>
    <p>
      <b>Stars:</b>
      {{ vueStars }}
    </p>
    <p>
      <b>Watchers:</b>
      {{ vueWatchers }}
    </p>
    <p>
      <b>Forks:</b>
      {{ vueForks }}
    </p>
    <h3>Angular</h3>
    <p>
      <b>Stars:</b>
      {{ angularStars }}
    </p>
    <p>
      <b>Watchers:</b>
      {{ angularWatchers }}
    </p>
    <p>
      <b>Forks:</b>
      {{ angularForks }}
    </p>
    <h3>Ember</h3>
    <p><b>Stars:</b></p>
    <p><b>Watchers:</b></p>
    <p><b>Forks:</b></p>
    <h3>Svelte</h3>
    <p><b>Stars:</b></p>
    <p><b>Watchers:</b></p>
    <p><b>Forks:</b></p>
    <h3>React</h3>
    <p><b>Stars:</b></p>
    <p><b>Watchers:</b></p>
    <p><b>Forks:</b></p>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";

export default {
  data: function () {
    return {
      vueStars: "",
      vueWatchers: "",
      vueForks: "",
      angularStars: "",
      angularWatchers: "",
      angularForks: "",
      emberStars: "",
      emberWatchers: "",
      emberForks: "",
      svelteStars: "",
      svelteWatchers: "",
      svelteForks: "",
      reactStars: "",
      reactWatchers: "",
      reactForks: "",
    };
  },
  created: function () {
    this.vueDetails();
    this.angularDetails();
    this.emberDetails();
    this.svelteDetails();
    this.reactDetails();
  },
  methods: {
    vueDetails() {
      axios.get("https://api.github.com/repos/vuejs/vue").then((response) => {
        this.vueStars = response.data.stargazers_count;
      });
      axios.get("https://api.github.com/repos/vuejs/vue").then((response) => {
        this.vueWatchers = response.data.watchers_count;
      });
      axios.get("https://api.github.com/repos/vuejs/vue").then((response) => {
        this.vueForks = response.data.forks_count;
      });
    },
    angularDetails() {
      axios.get("https://api.github.com/repos/angular/angular.js").then((response) => {
        this.angularStars = response.data.stargazers_count;
      });
      axios.get("https://api.github.com/repos/angular/angular.js").then((response) => {
        this.angularWatchers = response.data.watchers_count;
      });
      axios.get("https://api.github.com/repos/angular/angular.js").then((response) => {
        this.angularForks = response.data.forks_count;
      });
    },
  },
  name: "Home",
  components: {},
};
</script>
