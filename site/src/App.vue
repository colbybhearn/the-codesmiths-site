<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  
  
  //overflow: hidden;
}
body{
  margin:0px;
  background: rgb(36, 36, 36);
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: white;
    text-decoration: none;

    &.router-link-exact-active {
      color: white;
      text-decoration: none;
    }
  }
}
</style>
