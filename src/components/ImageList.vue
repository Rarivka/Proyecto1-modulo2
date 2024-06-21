<template>
    <div class="image-list p-4">
      <ul class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
        <li v-for="image in images" :key="image.date" @click="selectImage(image)" class="cursor-pointer">
          <img :src="image.url" :alt="image.title" class="w-full h-auto rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300" />
          <p class="text-center mt-2 text-lg font-semibold">{{ image.title }}</p>
        </li>
      </ul>
    </div>
</template>

<script>
    export default {
    name: 'ImageList',
    props: {
        images: Array,
        //required: true,
    },
    methods: {
        selectImage(image) {
        this.$emit('select-image', image);
        },
    },
    };
</script>

<style>
    /* .image-list ul {
    list-style-type: none;
    padding: 0;
    }

    .image-list li {
    display: inline-block;
    margin: 10px;
    cursor: pointer;
    }

    .image-list img {
    width: 200px;
    height: auto;
    } */
</style>