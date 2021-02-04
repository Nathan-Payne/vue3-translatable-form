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
        <p class="welcome-message">Good afternoon</p>
      </header>

      <form action="" @submit.prevent="submitForm">
        <div class="form-control">
          <label for="user-name">Username</label>
          <input
            id="user-name"
            name="user-name"
            type="text"
            v-model.trim="userName"
          />
        </div>

        <div class="form-control">
          <label for="password">Password</label>
          <input type="password" id="password" name="password" />
        </div>

        <div class="form-control">
          <button>
            Login
          </button>
        </div>
      </form>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      userName: null,
      password: null,
    }
  },
  methods: {
    submitForm() {
      //submission logic, POST req
      this.resetForm()
    },
    resetForm() {
      //reset all form elements
    },
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
  /* padding: 1rem 1rem; */
  margin: 2.5rem 2rem;
}

.form-control label {
  color: #555e63;
}

.form-control input {
  width: 21rem;
  /* height: 2.5rem; */
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
