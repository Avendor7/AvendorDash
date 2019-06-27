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
import axios from 'axios';
export default {
  name: 'Addresses',
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
  /* Position text in the middle of the page/image */
.custom-card {
  background-color: rgb(0,0,0); /* Fallback color */
  background-color: rgba(0,0,0, 0.4); /* Black w/opacity/see-through */
  color: white;
  font-weight: bold;
  border: 3px solid #f1f1f1;
  position: relative;
  text-align: center;
}


a {
  background-color: white;
  box-shadow: 5px 5px 5px black;
  color: black;
  padding: .5em .5em;
  margin: 1em .5em;
  position: relative;
  text-decoration: none;
  text-transform: uppercase;
  display: inline-block;
}
a span{
  padding:1em;
}
a:hover {
background-color: grey;
}

a:active {
box-shadow: none;
top: 5px;
}
ul{
  list-style-type: none;
  padding:0;
}
li {
  display: inline;
}
a img{
  vertical-align: middle;
  height:100%;
  width: 25px;
  
}
.searchbox{
  margin:20px;
}
.row{
  padding-bottom:20px;
}
</style>
