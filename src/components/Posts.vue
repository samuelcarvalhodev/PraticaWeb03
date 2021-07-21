<template>
  <div>
    <ul>
      <div v-for="user in users" :key="user.id">
        
          <li>
              <h1>Name: </h1>
                <p> {{ user.name }}</p>
                <div v-for="post in posts" :key="post.id" >
                    <div v-if="post.id % 2 != '0'">
                        <ul>
                        <li v-if="post.userId === user.id">
                            <p><strong>Title: </strong> {{ post.title }}</p>
                            <p><strong>Body: </strong> {{ post.body }}</p>
                            <h3>Comentarios:</h3>
                            <ul>
                                <div v-for="comment in comments" :key="comment.id">
                                    <li v-if="comment.postId === post.id">
                                        <p><strong>Email: </strong> {{ comment.email }}</p>
                                        <p><strong>Body: </strong> {{ comment.body }}</p>
                                    </li>
                                </div>
                            </ul>
                            <hr>
                        </li>
                        </ul>
                    </div>
                </div>

                
            </li>
        
      </div>
      
    </ul>
    <button @click="triggerFetch">Posts</button>
  </div>
</template>

<script>
export default {
  name: "Posts",
  data() {
    return {
      post: (Boolean = false),
      user: (Boolean = false),
      comment: (Boolean = false),
      posts: [],
      users: [],
      comments: [],
      postURI: "https://jsonplaceholder.typicode.com/posts",
      userURI: "https://jsonplaceholder.typicode.com/users",
      commentsURI: "https://jsonplaceholder.typicode.com/comments",
    };
  },
  methods: {
    fetchPosts: function() {
      this.$http.get(this.postURI).then((result) => {
        this.posts = result.data;
      });
    },
    fetchUser: function() {
      this.$http.get(this.userURI).then((result) => {
        this.users = result.data;
      });
    },
    fetchComments: function() {
      this.$http.get(this.commentsURI).then((result) => {
        this.comments = result.data;
      });
    },
    triggerFetch: function() {
      this.post = true;
      this.fetchPosts();
      this.fetchUser();
      this.fetchComments();
    },
  },
};
</script>

<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
