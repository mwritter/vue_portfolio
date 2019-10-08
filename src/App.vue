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
  justify-items: center;
  padding: 3rem 0;
  min-height: 100vh;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(
      to bottom right,
      rgba(75, 138, 184, 0.55) 50%,
      rgba(129, 217, 175, 0.62)
    )
    fixed;
}
#profile_picture {
  background: url("./assets/profile_picture.jpg") no-repeat;
  background-size: cover;
  background-position: center;
  border: 3px solid rgb(170, 197, 216);
  width: 200px;
  height: 200px;
  border-radius: 50%;
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
  border-radius: 1.2rem;
  -webkit-box-shadow: 5px 5px 25px 0px rgb(158, 158, 158);
  -moz-box-shadow: 5px 5px 25px 0px rgb(158, 158, 158);
  box-shadow: 5px 5px 25px 0px rgb(158, 158, 158);
  height: 200px;
}

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
</style>
