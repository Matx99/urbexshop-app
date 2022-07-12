<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <!-- <h1>LES GRANDES CATEGORIES</h1>
      <hr>
      <ul>
        <li v-for="category in categories" :key="category.id">
          <router-link :to="'/search?category=' + category.name"> -->
            <!-- <img :src="category.img !== null ? mediaRoot+category.img.path : 'https://hearhear.org/wp-content/uploads/2019/09/no-image-icon.png' " alt="" class="icon-category"> -->
            <!-- <p>{{ category.name }}</p> -->
          <!-- </router-link> -->
        <!-- </li>
      </ul> -->
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