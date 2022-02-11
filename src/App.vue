<template>
 <div class="app">
    <navbar />
    <div class="home__content">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Navbar from './components/UI/Navbar.vue'
export default {
  components: { Navbar },

}
</script>

<style>

@import url("https://fonts.googleapis.com/css2?family=Questrial&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Questrial", sans-serif;
}
body {
  position: relative;
  width: 100%;
}
ul {
  list-style: none;
}
a {
  text-decoration: none;
}
.home__content {
  position: absolute;
  left: 78px;
  height: 100%;
  width: calc(100% - 78px);
  transition: all 0.5s ease;
}
.container {
  padding: 15px 20px;
  width: 100%;
}
.sidebar.active ~ .home__content {
  width: calc(100% - 240px);
  left: 240px;
  transition: all 0.5s ease;
}


</style>