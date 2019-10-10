<template>
  <div class="info-section">
    <h3>Projects</h3>
    <transition name="fade" mode="out-in">
      <div id="project" :key="currentProject.title">
        <div id="project-image">
          <img :src="require(`../assets/${currentProject.image}`)" :alt="currentProject.title" />
        </div>
        <div id="project-info">
          <span class="heading">{{ currentProject.title }}</span>
          <div id="description">
            <h4>Description</h4>
            <span class="sub-heading">{{ currentProject.description }}</span>
          </div>
          <div id="tools">
            <h4>Tools</h4>
            <span class="sub-heading">{{ currentProject.tools | toolString }}</span>
          </div>
        </div>
      </div>
    </transition>

    <div id="controls">
      <div class="arrow-area" @click="prevProject()">
        <i class="lni-chevron-left size-sm"></i>
      </div>
      <div id="indicator">
        <div
          v-for="(project, index) in projects"
          :key="index"
          class="dot"
          :class="{'active-dot': index == currentIndex}"
        ></div>
      </div>
      <div class="arrow-area" @click="nextProject()">
        <i class="lni-chevron-right size-sm"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      next: true,
      prev: false,
      currentIndex: 0,
      projects: [
        {
          title: "Connecty",
          image: "connecty_preview.png",
          description:
            "Web Application built as a social media site for developers to connect.  Users can sign up and login, and are directed to a default profile page. Created UI with React components. Created backend endpoints to interact with MLab database. Implemented JWT token based authentication for logging in registered users. Deployed on Heroku.",
          tools: ["React", "Express", "Node", "Bootstrap", "Rest API", "Github"]
        },
        {
          title: "Ticket Event Web Application",
          image: "event-maker.png",
          description:
            "Web application for creating events and assigning tickets." +
            "Created web application in .NET and C#. Implemented fully responsive design for desktop and mobile.",
          tools: [".NET", "C#", "CSS", "Github"]
        },
        {
          title: "Weather Web App",
          image: "weather-preview.png",
          description:
            "Web Application built with React and Redux to get the temperature, pressure, and humidity from https://openweathermap.org/api, also uses Google Maps API to show searched location. Created UI with React components. Implemented API’s into React project. Managed web application state with Redux.",
          tools: ["React", "Redux", "Node", "Bootstrap", "API", "Github"]
        },
        {
          title: "Flutter Meal Plan App",
          image: "flutter_preview.png",
          description:
            "Cross-Platform application for create meal plans and a shopping list based on each meal plan. Contributed to and Managed code base using new framework – Flutter. Created a Cloud Database backend with Firebase and Firestore. Implemented Firebase Authentication to sign up and login users. Designed material-based UI and UX.",
          tools: ["Flutter", "Dart", "Github"]
        },
        {
          title: "Java Member Application",
          image: "java-preview.png",
          description:
            "Application for creating and maintaining groups with members. Worked with a team in an Agile environment to complete project. Managed issues, backlog, and assigning tasks to team members. Contributed to user friendly Graphical User Interface for project.",
          tools: ["Java", "JavaFX", "JUnit", "Github"]
        },
        {
          title: "Python Data Visualization",
          image: "python-1.png",
          description: "Packet transmission simulation, and data visualization",
          tools: ["Python", "Matplotlib", "Github"]
        }
      ]
    };
  },
  computed: {
    currentProject() {
      return this.projects[this.currentIndex];
    }
  },
  methods: {
    nextProject() {
      const n = this.projects.length;
      let index = this.currentIndex + 1;
      index = index % n;
      this.currentIndex = index;
    },
    prevProject() {
      const n = this.projects.length;
      let index = this.currentIndex - 1;
      if (index < 0) {
        index = ((index % n) + n) % n;
      } else {
        index = index % n;
      }
      this.currentIndex = index;
    }
  },
  filters: {
    toolString(value) {
      return value.join(" | ");
    }
  }
};
</script>

<style>
#project {
  display: grid;
  grid-template-columns: auto 1fr;
  grid-template-areas: "image info";
}
#project img {
  grid-area: image;
  margin: 1rem;
}
#project-info {
  grid-area: info;
}
#project-info h4 {
  margin-top: 0.75rem;
}
.heading {
  font-size: 2rem;
}
#controls {
  display: flex;
  justify-content: space-between;
  padding: 1rem;
  margin-top: 0.5rem;
}
#indicator {
  display: flex;
  align-self: center;
  justify-content: space-between;
}
.dot {
  border-radius: 50%;
  height: 0.5rem;
  width: 0.5rem;
  margin: 0 0.2rem;
  background-color: rgb(110, 110, 110);
  opacity: 0.2;
  cursor: pointer;
}
.active-dot {
  opacity: 1;
}
.arrow-area {
  padding: 0.4rem;
  font-size: 24;
  cursor: pointer;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave {
  opacity: 1;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity, 175ms ease-in-out;
}
</style>