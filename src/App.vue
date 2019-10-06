<template>
  <div id="app">
    <div id="profile_picture"></div>
    <h3>Hi my name's Matthew Ritter</h3>
    <Profile />
    <Contact />
  </div>
</template>

<script>
import Profile from "./components/Profile";
import Contact from "./components/Contact";
export default {
  name: "app",
  components: {
    Profile,
    Contact
  }
};
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
#app {
  display: grid;
  justify-items: center;
  padding: 3rem 0;
  height: 100%;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-image: linear-gradient(
    to bottom right,
    rgba(75, 138, 184, 0.55) 50%,
    rgba(129, 217, 175, 0.62)
  );
}
#profile_picture {
  background: url("./assets/profile_picture.jpg") no-repeat;
  background-size: cover;
  background-position: center;
  width: 100px;
  height: 100px;
  border-radius: 50%;
}
.info-section {
  display: flex;
  flex-direction: column;
  width: 100%;
  margin-top: 2rem;
  padding: 2rem 1rem;
  justify-content: center;
  text-align: center;
  background-color: rgba(232, 232, 232, 0.3);
  backdrop-filter: blur(10px);
}
.info-section .info-heading {
  justify-self: start;
}
</style>
