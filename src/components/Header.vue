<template>
  <div>
    <HeaderLogIn :user="user" v-if="token"></HeaderLogIn>
    <HeaderLogOut v-else></HeaderLogOut>
  </div>
</template>

<script>
import HeaderLogIn from "./HeaderLogIn";
import HeaderLogOut from "./HeaderLogOut";

export default {
  name: "Header",
  components: {
    HeaderLogIn,
    HeaderLogOut
  },
  data: function() {
    return {
      token: "",
      user: {}
    };
  },
  created() {
    this.token = localStorage.getItem("NOTES_AUTH");
    if (this.token) {
      this.user = {
        username: localStorage.getItem("username"),
        fullName: localStorage.getItem("full_name"),
        id: localStorage.getItem("id")
      };

      console.log(this.user);
    }
  }
};
</script>

<style scoped>
.header-style {
  padding: 30px 0;
  background: #ffffff;
  box-shadow: 0px 0px 27px rgba(230, 230, 230, 0.5);
}
.header-text {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: Roboto, sans-serif;
  font-size: 16px;
  margin: 0 auto;
  padding: 0 30px;
  max-width: 960px;
  color: #393939;
}

.link {
  text-decoration: none;
  color: #393939;
  text-transform: uppercase;
}
.nav-links ul {
  list-style-type: none;
  display: flex;
  flex-direction: row;
  padding: 0;
  margin: 0;
  justify-content: center;
}
.nav-links a {
  margin-left: 40px;
}
.nav-links ul li:first-child a {
  margin-left: 0px;
}
a:hover {
  color: #050505;
}
.logo {
  height: 42px;
  display: flex;
  justify-content: center;
}

@media screen and (max-width: 900px) {
  .header-text {
    display: flex;
    flex-direction: column;
  }
  .logo,
  .link,
  .nav-links {
    width: 100%;
  }
  .logo {
    order: -1;
  }
  .nav-links ul {
    justify-content: center;
  }

  .logo {
    margin-bottom: 30px;
  }

  .link {
    display: inline-block;
    margin-bottom: 20px;
  }
}

@media screen and (max-width: 400px) {
  .nav-links ul {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .nav-links ul li a {
    margin: 5px 0;
  }
}
</style>