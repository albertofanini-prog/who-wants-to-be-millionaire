<template>
  <router-view/>
</template>

<style lang="scss">
//font
@import url('https://fonts.googleapis.com/css2?family=Mingzat&family=Roboto:wght@300&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Arvo&family=Josefin+Sans:wght@300&family=Mingzat&family=Roboto:wght@300&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  // height: 100vh;
}

#app {
  font-family: 'Arvo', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100vh;
}

nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
