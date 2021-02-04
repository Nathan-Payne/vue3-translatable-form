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
  font-family: 'Roboto', sans-serif;
  font-size: 1rem;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #eeeeee;
}

button {
  padding: 0.8rem 1rem;
  margin-top: 0.25rem;
  margin-bottom: 0.25rem;
  background-color: #ff4282;
  color: white;
  text-transform: uppercase;
  border: none;
  border-radius: 6px;
}
</style>
