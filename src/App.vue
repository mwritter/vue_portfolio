<template>
  <div id="app">
    <div id="profile_picture"></div>
    <h3>Hi my name's Matthew Ritter</h3>
    <Profile />
    <Projects />
    <Contact />
  </div>
</template>

<script>
import Profile from "./components/Profile";
import Contact from "./components/Contact";
import Projects from "./components/Projects";
export default {
  name: "app",
  components: {
    Profile,
    Contact,
    Projects
  }
};
</script>

<style>
:root {
  --shadow-color: rgba(116, 116, 116, 0.932);
}
html,
body {
  height: 100%;
}
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
#app {
  display: grid;
  grid-gap: 1rem;
  justify-items: center;
  padding: 3rem 0;
  min-height: 100vh;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  font-family: "Roboto", "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(
      to bottom right,
      rgba(52, 143, 207, 0.55) 35%,
      rgba(135, 202, 168, 0.5)
    )
    fixed;
}
#profile_picture {
  background: url("./assets/profile_picture.jpg") no-repeat;
  background-size: cover;
  background-position: center;
  width: 12rem;
  height: 12rem;
  border-radius: 50%;
  -webkit-box-shadow: 5px 5px 15px 0px var(--shadow-color);
  -moz-box-shadow: 5px 5px 15px 0px var(--shadow-color);
  box-shadow: 5px 5px 15px 0px var(--shadow-color);
}

.info-section {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin-top: 2rem;
  padding: 2rem 1rem;
  justify-content: center;
  background-color: rgba(232, 232, 232, 0.3);
  backdrop-filter: blur(10px);
}
.info-section .info-heading {
  justify-self: start;
}

.info-section #project img {
  opacity: 1;
  transition: opacity 500ms;
  border-radius: 1.2rem;
  -webkit-box-shadow: 5px 5px 10px 0px var(--shadow-color);
  -moz-box-shadow: 5px 5px 10px 0px var(--shadow-color);
  box-shadow: 5px 5px 10px 0px var(--shadow-color);
  height: 12rem;
}

/* For desktop or larger than mobile */
@media screen and (min-width: 700px) {
  #app {
    padding: 3rem 2rem;
  }
  .info-section {
    justify-content: center;
    border-radius: 1.2rem;
    max-width: 50rem;
  }
  #contact-form {
    align-self: center;
    width: 80%;
    max-width: 500px;
  }
  #contact-form #submit {
    justify-self: start;
    padding: 0.75rem 1.5rem;
  }
}
/* For mobile */
@media screen and (max-width: 700px) {
  #description {
    display: none;
  }
  #project {
    grid-template-columns: 1fr;
    height: 25rem;
    justify-content: center;
    text-align: center;
    grid-template-areas:
      "image"
      "info";
  }
  .badge-row {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
  }
  .info-section #project img {
    height: 10rem;
  }
}
</style>
