<template>
  <div >
      <ul>
          <div v-for="album in albums" :key="album.id" >
              <li>
                  <h1>Title: </h1>
                  <p>{{ album.title }}</p>
                  <div v-for="photo in photos" :key="photo.id">
                      <!-- <ul> -->
                          <div v-if="photo.albumId === album.id">
                            <p><strong>Photo title: </strong> {{ photo.title }} </p>
                            <img v-bind:src="photo.url" v-bind:alt="Imagem">
                          </div>
                          <hr>
                      <!-- </ul> -->
                  </div>
              </li>
          </div>
      </ul>
      <button @click="triggerMethods">Photos</button>
 </div>
</template>

<script>
export default 
{ 
    name: "Albums",
    data() {
        return {
            album: (Boolean = false),

            photos: [],
            user: [],
            albums: [],
            photosURI: "https://jsonplaceholder.typicode.com/photos",
            userURI: "https://jsonplaceholder.typicode.com/users",
            albumsURI: "https://jsonplaceholder.typicode.com/albums"
            };
        },
        methods: {
            fetchPhotos: function() {
                this.$http.get(this.photosURI).then((result) => {
                    this.photos = result.data;    
                });
            },
            fetchUser: function() {
                this.$http.get(this.userURI).then((result) => {
                    this.users = result.data;
                });
            },
            fetchAlbums: function(){
                this.$http.get(this.albumsURI).then((result) => {
                    this.albums = result.data;
                });
            },
            triggerMethods: function(){
                this.album = true;
                this.fetchPhotos();
                this.fetchUser();
                this.fetchAlbums();
            }
            
        },
};
</script>

<style>

</style>