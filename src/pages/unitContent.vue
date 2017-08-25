<template>
  <main-layout>
    <content-item></content-item>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue';
  import ContentItem from '../components/unitContentItem.vue';

  export default {
    components: {
      MainLayout,
      ContentItem
    }
  }
</script>

<style>

</style>

