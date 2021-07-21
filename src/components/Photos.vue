<template>
  <div>
      <ul>
          <div v-for="photo in photos" :key="photo.id">
              <div v-if="photo.albumId == '3'">
                <li>
                    <p><strong>AlbumId: </strong>{{ photo.albumId }}</p>
                    <img v-bind:src="photo.thumbnailUrl" v-bind:alt="Imagem">
                    
                </li>
                </div>
          </div>
      </ul>
      <button @click="fetchPhotos">Photos</button>
 </div>
</template>

<script>
export default 
{ 
    name: "Photos",
    data() {
        return {
            photos: [],
            baseURI: "https://jsonplaceholder.typicode.com/photos"   
            };
        },
        methods: {
            fetchPhotos: function() {
                this.$http.get(this.baseURI).then((result) => {
                    this.photos = result.data;    
                });
            },
        },
};
</script>

<style>

</style>