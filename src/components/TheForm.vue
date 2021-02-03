<template>
  <main>
    <div class="form">
      <header>
        <div class="icon"></div>
        <p>Good afternoon</p>
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

        <button>
          Login
        </button>
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
}

.form-control {
}
</style>
