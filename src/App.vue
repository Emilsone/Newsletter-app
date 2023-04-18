<template>
  <div id="app">
    <NewsLetter />
  </div>
</template>

<script>
import NewsLetter from './components/NewsLetter.vue'
// import {db} from '@/firestoreInit'

export default {
  name: 'App',
  components: {
    NewsLetter
  }
} 
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Work+Sans&display=swap');
#app {
  font-family: 'Work Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
