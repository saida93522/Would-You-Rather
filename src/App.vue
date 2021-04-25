<template>
  <div id="app">
    <h1>Would you rather...</h1>
    <would-you-rather
      v-bind:question="wyrQuestion"
      v-bind:answer1="wyrAnswer1"
      v-bind:answer2="wyrAnswer2"
      v-on:answer-changed="answerChanged"
    >
    </would-you-rather>
    <!-- preffered -->

    <p class="user">{{ userMsg }}</p>
  </div>
</template>

<script>
import WouldYouRather from "./components/WouldYouRather.vue";

export default {
  name: "App",
  components: {
    WouldYouRather,
  },
  data() {
    return {
      wyrQuestion: "Would you rather be incredibly funny or incredibly smart?",
      wyrAnswer1: "Incredibly funny",
      wyrAnswer2: "Incredibly smart",
      userMsg: "",
    };
  },
  methods: {
    answerChanged(choice) {
      this.userMsg = `Thanks! You chose ${choice}`;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.user {
  font-weight: bold;
  color: rgb(124, 177, 124);
}
</style>
