<template>
  <div id="app">
    <HeaderLogIn :user="user" v-if="token"/>
    <router-view></router-view>
  </div>
</template>

<script>
import HeaderLogIn from "./components/HeaderLogIn";

export default {
  name: "App",
  components: {
    HeaderLogIn
  },
  data() {
    return {
      token: "",
      user: {}
    };
  },
  created() {
    this.token = localStorage.getItem("NOTES_AUTH");

    if (this.token) {
      this.user = {
        username: localStorage.getItem("USER_NAME"),
        fullName: localStorage.getItem("FULL_NAME"),
        id: localStorage.getItem("USER_ID")
      };

      console.log(this.user);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
