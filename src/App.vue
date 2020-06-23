<template>
  <div id="app">
    <div class="header" :style="{backgroundImage: `url('${headerImage}')`}"></div>
    <Profile style="margin-top: 150px" />

    <div class="disclaimer">
      <b>Disclaimer:</b> all data comes from
      <a href="https://npmjs.com/package/faker">Faker</a>, a JS library for
      generating placeholder data. All names and company names are fake, and any
      resemblance to real-life people or companies is accidental.
    </div>
  </div>
</template>

<script>
import Profile from "./components/Profile.vue";
import faker from "faker"

export default {
  name: "App",
  components: {
    Profile,
  },
  data() {
    return {
      headerImage: "https://cdn.pixabay.com/photo/2020/06/17/19/20/gorge-5310788_960_720.jpg"
    }
  }
};
</script>

<style>
html,
body,
#app {
  height: 100%;
  margin: 0;
  overflow: auto;
}

@import url("https://fonts.googleapis.com/css2?family=Jost:wght@300;400;700&display=swap");

#app {
  text-align: center;
  font-family: "Jost", sans-serif;
}

.header {
  background-color: lightgray;
  background-position: center center;
  background-size: cover;

  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 300px;
  z-index: -1;

  /* mask-image: linear-gradient(to bottom, black 75%, transparent); */
  border-bottom-left-radius: 70px;
  border-bottom-right-radius: 70px;
}

.disclaimer {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  text-align: center;
  padding: 5px;
  background-color: white;
  color: rgb(100, 100, 100);
  font-size: 15px;
}
.disclaimer b {
  color: black;
}
</style>
