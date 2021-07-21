<template>
  <div >
      <ul>
          <div v-for="todo in todos" :key="todo.id">
              <li v-if="todo.completed === true">

                  <h1>Title todo: </h1>
                  <p> {{ todo.title }} </p>
                  <div >
                      <!-- //v-for="user in users " :key="user.id" -->
                    <div >
                        <div v-if=" todo.userId === users.id ">
                        <p><strong>User: </strong> {{ user.name }} </p>
                        </div>
                        <p><strong>Completed: </strong> {{ todo.completed }}</p>
                    </div>
                    </div>
              </li>
          </div>
      </ul>
      <button @click="triggerMethods">Todos</button>
 </div>
</template>

<script>
export default 
{ 
    name: "Todos",
    data() {
        return {
            todos: [],
            users: [],
            todosURI: "https://jsonplaceholder.typicode.com/todos",
            userURI: "https://jsonplaceholder.typicode.com/users",   
            };
        },
        methods: {
            fetchTodos: function() {
                this.$http.get(this.todosURI).then((result) => {
                    this.todos = result.data;    
                });
            },
            fetchUser: function() {
                this.$http.get(this.userURI).then((result) => {
                    this.users = result.data;
                });
            },
            triggerMethods: function(){
                this.fetchUser();
                this.fetchTodos();
            }
        },
};
</script>

<style>

</style>