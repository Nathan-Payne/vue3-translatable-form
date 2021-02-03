<template>
  <the-header>
    <template #logo>
      <h1>App Logo</h1>
    </template>

    <template #controls>
      <button>It's Pirate Day!</button>
      <button>English</button>
      <button>French</button>
    </template>
  </the-header>

  <the-form></the-form>
</template>

<script>
import TheForm from './components/TheForm.vue'
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    TheForm,
    TheHeader,
  },
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
