<template>
  <div>
      <ul>
          <div v-for="comment in comments" :key="comment.id">
              <div v-if="comment.id%2 == '0' ">
                <li>
                    <p><strong>Id: </strong> {{ comment.id }}</p>
                    <p><strong>PostId: </strong> {{ comment.postId }}</p>
                    <p><strong>Name: </strong> {{ comment.name }}</p>
                    <p><strong>E-mail: </strong> {{ comment.email }}</p>
                    <p><strong>Body: </strong> {{ comment.body }}</p>
                    </li>
                </div>
          </div>
      </ul>
      <button @click="fetchComments">Comments</button>
 </div>
</template>

<script>
export default 
{ 
    name: "Comments",
    data() {
        return {
            comments: [],
            baseURI: "https://jsonplaceholder.typicode.com/comments"   
            };
        },
        methods: {
            fetchComments: function() {
                this.$http.get(this.baseURI).then((result) => {
                    this.comments = result.data;    
                });
            },
        },
};
</script>

<style>

</style>