<template>
  <div id="addresses" class="custom-card">
        <h1>Press START to Continue</h1>
        <ul>
          <li v-for="value in addresses" :key="value.name">
            <a v-bind:href="value.url"><img v-bind:src="value.favicon"><span>{{value.name}}</span></a>
          </li>
        </ul>
      </div>
</template>

<script>
export default {
  el: '#addresses',
  data () {
      return {
        addresses: []
      }
    },
    mounted () {
      axios
        .get('https://gist.githubusercontent.com/Avendor7/c2ee64a8fdab047766f1a54b9b0ba592/raw/d95e708e784f3f0495682c4fdd7f9ea28d83a60d/settings.json')
        .then(response => (this.addresses = response.data.addresses))
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
