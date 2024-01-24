<template>
  <div>
    <router-view />
  </div>
</template>

<script>
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100&display=swap");
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.navbar {
  height: 92px;
}
.logo {
  line-height: 96px;
  /* left: 0; */
  width: 85px;
  height: 69px;
}
.text-laptop,
.text-desktop,
.text-network,
.text-printer,
.text-pc,
.text-all,
.text-repair {
  line-height: 96px;
  font-weight: 600;
  font-style: 14px;
  text-align: center;
  color: #000000;
}

.banner {
  height: 104px;
  width: 1190px;
  text-align: center;
}
nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
