<!-- src/App.vue -->
<template>
  <div id="app">
    <Sidebar />
    <router-view />
  </div>
</template>

<script>
import Sidebar from '@/components/SideBar.vue';

export default {
  name: 'App',
  components: {
    Sidebar,
  },
};
</script>

<style>
/* Your styles here */
</style>
