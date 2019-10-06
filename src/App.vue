<template>
  <div id="app">
    <div id="profile_picture"></div>
    <h3>Hi my name's Matthew Ritter</h3>
  </div>
</template>

<script>
export default {
  name: "app",
  components: {}
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
  height: 100vh;
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
  width: 200px;
  height: 200px;
  border-radius: 50%;
}
</style>
