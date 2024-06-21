<template>
    <div class="flex flex-col items-center">
      <img :src="image.href" alt="Imagen de la NASA" class="object-cover w-full h-64 mb-4" />
      <div class="text-center">
        <h2 class="font-bold text-lg">{{ image.title }}</h2>
        <p class="text-gray-600">{{ image.description }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      image: Object,
    },
  };
  </script>
  