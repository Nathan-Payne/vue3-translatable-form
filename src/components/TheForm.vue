<template>
  <main>
    <div class="form">
      <header>
        <div class="icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="35"
            height="35"
            fill="currentColor"
            viewBox="0 0 16 16"
          >
            <path
              d="M3 14s-1 0-1-1 1-4 6-4 6 3 6 4-1 1-1 1H3zm5-6a3 3 0 1 0 0-6 3 3 0 0 0 0 6z"
            />
          </svg>
        </div>
        <p class="welcome-message">{{ languageLabels.welcome_message }}</p>
      </header>

      <form action="" @submit.prevent="submitForm">
        <div class="form-control">
          <label for="user-name">{{ languageLabels.username_label }}</label>
          <input
            id="user-name"
            name="user-name"
            type="text"
            v-model.trim="userName"
          />
        </div>

        <div class="form-control">
          <label for="password">{{ languageLabels.password_label }}</label>
          <input
            type="password"
            id="password"
            name="password"
            v-model="password"
          />
        </div>

        <div class="form-control">
          <button>{{ languageLabels.login_label }}</button>
        </div>
      </form>
    </div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  props: {
    loginLanguage: {
      type: String,
      default: 'english',
    },
  },
  data() {
    return {
      userName: null,
      password: null,
      languageLabels: {},
    }
  },
  watch: {
    loginLanguage() {
      this.getLanguageLabels()
    },
  },
  methods: {
    submitForm() {
      //submission/validation logic -> POST req
      this.resetForm()
    },
    resetForm() {
      //clears all form inputs
      this.userName = ''
      this.password = ''
    },
    async getLanguageLabels() {
      // can remove demo button and check dateToday === datePirateDay to run automatically
      if (this.loginLanguage === 'pirate') {
        const englishDefault = await axios.get('/languages/english.json')
        const pirateLanguage = await axios.get('/languages/pirate.json')
        this.languageLabels = { ...englishDefault.data, ...pirateLanguage.data }
      } else {
        const languageData = await axios.get(
          `/languages/${this.loginLanguage}.json`
        )
        this.languageLabels = languageData.data
      }
    },
  },
  created() {
    this.getLanguageLabels()
  },
}
</script>

<style scoped>
main {
  height: 100vh;
  display: grid;
  place-items: center;
  font-size: 1.2rem;
}

.form {
  max-width: 30rem;
  background-color: white;
  border-radius: 0 0 8px 8px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
    0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

.form header {
  background-color: #555e63;
  color: white;
  padding: 1.6rem 1.5rem;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.form header .icon {
  position: absolute;
  top: -22%;
  background-color: #555e63;
  box-shadow: 0 0 0 8px #eeeeee;
  border-radius: 50%;
  padding: 0.35rem 0.4rem;
}

.form header .welcome-message {
  padding-top: 1.5rem;
}

.form-control {
  display: flex;
  flex-direction: column;
  margin: 2.5rem 2rem;
}

.form-control label {
  color: #555e63;
}

.form-control input {
  width: 21rem;
  line-height: 1.5rem;
  font-size: 1.5rem;
  padding: 5px;
  margin-top: 0.5rem;
  background-color: #eeeeee;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 4px;
}

.form-control input:focus {
  outline: none;
  box-shadow: 0 0 0.1rem 0.1rem rgba(0, 123, 255, 0.25);
}

.form-control button {
  width: 50%;
  margin-top: 0;
  font-size: 1.2rem;
}
</style>
