<template>
    <div class="grid grid-cols-3 gap-4">
      <component-image-item v-for="image in images" :image="image" :key="image.nasa_id" @click="onSelectImage" />
      <div v-if="loading" class="text-center p-4">Cargando...</div>
    </div>
  </template>
  
  <script>
  import ComponentImageItem from "./NasaImageDetail.vue";
  
  export default {
    props: {
      images: Array,
      loading: Boolean,
    },
    methods: {
      onSelectImage(image) {
        this.$emit("selectImage", image);
      },
    },
  };
  </script>
  