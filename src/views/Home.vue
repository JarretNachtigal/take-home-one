<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h1>Github Watcher Take Home</h1>
    <h1>{{ test }}</h1>
    <h2>Frameworks:</h2>
    <h3>Vue</h3>
    <p>
      <b>Stars:</b>
      {{ vueStars }}
    </p>
    <p><b>Watchers:</b></p>
    <p><b>Forks:</b></p>
    <h3>Angular</h3>
    <p><b>Stars:</b></p>
    <p><b>Watchers:</b></p>
    <p><b>Forks:</b></p>
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
  return: {
    test: "",
    vueStars: "",
  },
  created: function () {
    axios.get("https://api.github.com/zen").then((response) => {
      this.test = response.data;
    });
    axios.get("https://api.github.com/repos/vuejs/vue").then((response) => {
      this.vueStars = response;
    });
  },
  methods: {},
  name: "Home",
  components: {},
};
</script>
