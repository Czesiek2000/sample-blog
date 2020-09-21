<template>
  <Hero />
  <Posts v-bind:posts="posts"/>
</template>

<script>
import Hero from './components/Hero';
import Posts from './components/Posts';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    Hero,
    Posts
  },
  data () {
    return {
      posts: []
    }
  },
  created() {
    axios.get('http://jsonplaceholder.typicode.com/posts?_limit=15')
    .then(res => this.posts = res.data)

    .catch(err => console.log(err))
  }
}
</script>

<style>
body, html {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
