<template>
  <div class="bg-image"></div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bg-image {
  /* The image used */
  background-image: url("./../assets/rpi.jpg");

  /* Add the blur effect */
  filter: blur(12px);
  -webkit-filter: blur(12px);
  transform: scale(1.1);

  /* Full height */
  height: 100%; 
  width: 100%;

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position:fixed;
}
</style>
