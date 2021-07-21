<template>
  <div>
      <ul>
          <div v-for="todo in todos" :key="todo.id">
              <div v-if="todo.userId == '2'">
                  <div v-if="todo.completed == true">
                    <li>
                        <p><strong>UserId: </strong> {{ todo.userId }}</p>
                        <p><strong>Id: </strong> {{ todo.id }}</p>
                        <p><strong>Title: </strong> {{ todo.title }}</p>
                        <p><strong>Completed: </strong> {{ todo.completed }}</p>
                    </li>
                    </div>
              </div>
          </div>
      </ul>
      <button @click="fetchTodos">Todos</button>
 </div>
</template>

<script>
export default 
{ 
    name: "Todos",
    data() {
        return {
            todos: [],
            baseURI: "https://jsonplaceholder.typicode.com/todos"   
            };
        },
        methods: {
            fetchTodos: function() {
                this.$http.get(this.baseURI).then((result) => {
                    this.todos = result.data;    
                });
            },
        },
};
</script>

<style>

</style>