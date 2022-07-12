<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import axios from "axios";


export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    const headers = {
    'Content-type': 'application/json',
    // 'Authorization': 'Bearer '+token
    } 
    return axios.get("https://localhost/greetings",null,{headers})
    .then(response => {
      console.log(response.data);
    }).catch(e => console.log(e))
  
  // return await axios.patch(url+`/users/${id}`,data, {headers});
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
  margin-top: 60px;
}
</style>