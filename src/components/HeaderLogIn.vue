<template>
  <header class="header-style">
    <div class="header-text">
      <div class="name">
        <span class="link">{{user.fullName || user.username}}</span>
      </div>

      <div class="logo">
        <router-link to="/dashboard">
          <img src="/assets/logo.svg" alt="Logo">
        </router-link>
      </div>

      <div class="nav-links">
        <ul>
          <li>
            <router-link to="/settings" class="link">SETTINGS</router-link>
          </li>
          <li>
            <router-link to="/help" class="link">HELP</router-link>
          </li>
          <li>
            <router-link to="/sign-out" class="link">SIGN OUT</router-link>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderLogIn",
  props: ["user"]
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