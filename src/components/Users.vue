<template>
  <div>
      <ul>
          <h2>Desenvolvimento de Software para WEB - Atividade III</h2>
          <div v-for="user in users" :key="user.id">
              <div v-if="user.id <'6' "> 
                <li> 
                    <p><strong>Id: </strong>{{user.id }}</p>
                    <p><strong>Name: </strong>{{user.name }}</p>
                    <p><strong>Username: </strong>{{ user.username }}</p>
                    <p><strong>E-mail: </strong>{{ user.email }}</p>

                    <p><strong>Address: </strong>{{user.address.street }}, {{user.address.suite }}, {{user.address.city }}, {{user.address.zipcode }} - 
                        geo: {{user.address.geo.lat }}, {{user.address.geo.lng }}.
                    </p>

                    <p><strong>Phone: </strong>{{user.phone }}</p>
                    <p><strong>Website: </strong>{{user.website }}</p>

                    <p><strong>Company: </strong>{{user.company.name }}, {{user.company.catchPhrase }}, {{user.company.bs }}.</p>
                    
                </li>
              </div>
          </div>
      </ul>
      <button @click="fetchUsers">Users</button>
 </div>
</template>

<script>
export default 
{ 
    name: "Users",
    data() {
        return {
            users: [],
            baseURI: "https://jsonplaceholder.typicode.com/users"   
            };
        },
        methods: {
           fetchUsers: function() {
                this.$http.get(this.baseURI).then((result) => {
                    this.users = result.data;    
                });
            },
        },
};
</script>

<style>

</style>