<template>
  <div class="container mx-auto p-4 space-y-4" id="app">
    <img src="./assets/logo.png" alt="NASA" class="w-32 mx-auto" />
    <h1 class="text-3xl font-semibold mb-4">Galeria de Imagenes de la NASA</h1>
    <ImageList @select-image="fetchImageDetails" :images="images" />
    <ImageDetails v-if="selectedImage" :image="selectedImage" />
  </div>
</template>

<script>
import axios from 'axios';
import ImageList from './components/ImageList.vue';
import ImageDetails from './components/ImageDetails.vue';

export default {
  name: 'App',
  components: {
    ImageList,
    ImageDetails,
  },
  data() {
    return {
      images: [],
      selectedImage: null,
    };
  },
  created() {
    this.fetchImages();
  },
  methods: {
    async fetchImages() {
      const apiKey = 'tG5p2YomhVGZZ2RZdjbeQTWTPu2e3qyx3aeXuNQx';
      try {
        const response = await axios.get(`https://api.nasa.gov/planetary/apod?api_key=${apiKey}&count=10`);
        if (Array.isArray(response.data)) {
          this.images = response.data;
        } else {
          this.images = [response.data]; // Asegúrate de que sea un array
        }
        console.log("planetary", this.images);
      } catch (error) {
        console.error(error);
      }
    },
    fetchImageDetails(image) {
      this.selectedImage = image;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #151268;
  margin-top: 60px;
}
</style>

