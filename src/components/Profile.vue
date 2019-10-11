<template>
  <div class="info-section">
    <p>
      I'm a creator. I like to build things and I use software development to do just that. These are the technologies I'm currently working with and have used in my own projects. I'm always
      finding new tools to solve problems, which means I'm always learning new things and I love that about software development.
    </p>
    <p>{{totalWidth}}</p>

    <div class="badge-row">
      <div class="badge" v-for="(badge, index) in badges" :key="index">
        <img :src="require(`../assets/${badge.image}`)" :alt="badge.title" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      rowCount: 1,
      totalWidth: window.innerWidth,
      badges: [
        {
          image: "js_badge.png",
          title: "JavaScript"
        },
        {
          image: "html_badge.png",
          title: "HTML"
        },
        {
          image: "css_badge.png",
          title: "CSS"
        },
        {
          image: "react_badge.png",
          title: "React"
        },
        {
          image: "redux_badge.png",
          title: "Redux"
        },
        {
          image: "node_badge.png",
          title: "Node"
        },
        {
          image: "vue_badge.png",
          title: "VueJS"
        },
        {
          image: "python_badge.png",
          title: "Python"
        },
        {
          image: "java_badge.png",
          title: "Java"
        },
        {
          image: "dart_badge.png",
          title: "Dart"
        },
        {
          image: "flutter_badge.png",
          title: "Flutter"
        },
        {
          image: "C_badge.png",
          title: "C#"
        }
      ]
    };
  }
};
</script>

<style>
.badge-row {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  justify-content: center;
  margin-top: 1rem;
  padding-left: 1rem;
}
.badge img {
  height: 2.5rem;
}
</style>