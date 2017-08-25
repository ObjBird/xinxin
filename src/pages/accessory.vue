<template>
  <main-layout>
    <accessory-item></accessory-item>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue';
  import AccessoryItem from '../components/accessoryItem.vue';

  export default {
    components: {
      MainLayout,
      AccessoryItem
    }
  }
</script>
