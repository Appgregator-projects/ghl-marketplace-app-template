<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="yahemhahhhh to Your Vue.js App"/>
    
    <!-- Display user data -->
    <div v-if="userData">
      <h2>User Details</h2>
      <pre>{{ userData }}</pre>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      userData: null
    }
  },
  async mounted() {
    try {
      this.userData = await window.ghl.getUserData();
    } catch (error) {
      console.error('Error fetching user data:', error);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>