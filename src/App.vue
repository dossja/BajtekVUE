<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link :to="{ name: 'About' }">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #cad9e9;
  background: #2c3e50;
}

#nav {
  padding: 30px;
  background: #1a2530;
  margin: 0px 50px;
}

#nav a {
  font-weight: bold;
  color: #94b3d1;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
