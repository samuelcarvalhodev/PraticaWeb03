<template>
  <div id="app">
    <h1>Prática 03 de Web</h1>
    <div class="body" >
      <Todos></Todos>
      <hr>
      <Albums></Albums>
      <hr>
      <Posts></Posts>
    </div>
  </div>
</template>

<script>
import Users from './components/Users.vue';
import Todos from './components/Todos.vue';
import Albums from './components/Albums.vue';
import Comments from './components/Comments.vue';
import Posts from './components/Posts.vue';

export default {
   name: "App",
   components:{
    Users,
    Todos,
    Albums,
    Comments,
    Posts
   }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #32264D;
 
 

}

#app button {
  width: 120px;
  height: 30px;
  margin-bottom: 10px;
  border-radius: 5px;
  border: none;
  background-color: #04D361;
  transition: background-color, width, height 0.3s;
}

#app button:hover{
  cursor: pointer;
  background-color: #04BF58;
  height: 35px;
  width: 125px;
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

#app .body{
  /* border: 1px solid #000; */
  display: flex;
  background-color: #f7f7f7;
  height: 100vh;
}

hr{
  height: 10%;
}

li {
  background: #e8e9e8;
  margin: 10px 350px 10px 350px;
  border-radius: 8px;
}
li img {
  width: 150px;
  height: 150px;
}
 h2 {
  
   margin: 100px 0 80px 0;
   font-size: 30px;
 }

</style>
