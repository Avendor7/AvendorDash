<template>
  <div id="app">
    <BackgroundImage/>
      <div class="row">
        <Bookmarks/>
      </div>
  </div>
</template>

<script>
import BackgroundImage from './components/BackgroundImage.vue';
import Bookmarks from './components/Bookmarks.vue';

export default {
  name: 'app',
  components: {
    BackgroundImage,
    Bookmarks
  }
}
</script>

<style>



</style>
