<template>
  <the-header>
    <template #logo>
      <h1>App Logo</h1>
    </template>

    <template #controls>
      <button @click="setPirate">It's Pirate Day!</button>
      <button @click="setEnglish">English</button>
      <button @click="setFrench">French</button>
    </template>
  </the-header>

  <the-form :login-language="loginLanguage"></the-form>
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
  data() {
    return {
      loginLanguage: 'english',
    }
  },
  methods: {
    setPirate() {
      this.loginLanguage = 'pirate'
    },
    setEnglish() {
      this.loginLanguage = 'english'
    },
    setFrench() {
      this.loginLanguage = 'french'
    },
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
  padding: 0.8rem 0.8rem;
  margin-top: 0.25rem;
  margin-bottom: 0.25rem;
  background-color: #ff4282;
  color: white;
  text-transform: uppercase;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: all 200ms ease-out;
}

button:hover {
  background-color: #f80e5c;
  transition: all 200ms ease-out;
}

button:focus {
  outline: none;
}
</style>
