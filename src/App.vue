<template>
  <v-app>
    <div id="app">
      <div>
        <div id="nav">
          <router-link to="/">Home</router-link> |
          <router-link to="/about">About</router-link> |
          <router-link to="/user">User</router-link> |
          <router-link to="/agence">Agence</router-link> |
          <router-link to="/myagence">MyAgence</router-link> |
          <router-link to="/manage">Manage</router-link> 
        </div>
        <div>
          <ConnectionCreate/>
        </div>
      </div>
      <router-view/>
    </div>
  </v-app>
</template>

<script>
import ConnectionCreate from './components/connect/ConnectionCreate';
export default {
  components:{
    ConnectionCreate
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
