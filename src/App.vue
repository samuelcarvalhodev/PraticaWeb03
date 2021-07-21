<template>
  <div id="app">
    <Users></Users>
    <Todos></Todos>
    <Photos></Photos>
    <Comments></Comments>
    <Posts></Posts>
  </div>
</template>

<script>
import Users from './components/Users.vue';
import Todos from './components/Todos.vue';
import Photos from './components/Photos.vue';
import Comments from './components/Comments.vue';
import Posts from './components/Posts.vue';

export default {
   name: "App",
   components:{
    Users,
    Todos,
    Photos,
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
  color: #2c3e50;
  
}

#app button {
  width: 120px;
  height: 30px;
  margin-bottom: 10px;
  border-radius: 5px;
  
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
