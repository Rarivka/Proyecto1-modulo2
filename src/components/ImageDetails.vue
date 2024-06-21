<template>
    <div class="image-details p-4">
      <h2 class="text-2xl font-bold mb-4">{{ image.title }}</h2>
      <img :src="image.url" :alt="image.title" class="w-full h-auto rounded-lg shadow-md mb-4" />
      <p class="text-sm font-semibold">{{ image.explanation }}</p>
      <p class="mt-4 text-lg text-gray-600"><strong>Date:</strong> {{ image.date }}</p>
    </div>
</template>
  
  <script>
  export default {
    name: 'ImageDetails',
    props: {
      image: Object,
    },
  };
  </script>
  
  <style>
  /* .image-details {
    margin-top: 20px;
  }
  
  .image-details img {
    max-width: 100%;
    height: auto;
  } */
  </style>