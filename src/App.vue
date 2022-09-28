<template>
  <div id="app">
    <input type="text" @input="search" v-model="searchInput" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  data() {
    return {
      searchInput: '',
      mytimeout: 0,
    };
  },
  components: {
    HelloWorld,
  },
  methods: {
    search() {
      console.log('search', this.searchInput);
      if (this.mytimeout) clearTimeout(this.mytimeout);
      this.mytimeout = setTimeout(() => {
        console.log('action called');
      }, 500);
      console.log(this.mytimeout, 'mytimeout');
    },
  },
};
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
