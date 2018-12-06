<template>
<div class="flex-center">
  <div class="login-form">
    <h2 class="login-heading">Register</h2>
    <form action="#" @submit.prevent="register">

      <div class="form-control">
        <label for="name">Name</label>
        <input type="text" name="name" id="name" class="login-input" v-model="name">
      </div>

      <div class="form-control">
        <label for="email">Email</label>
        <input type="email" name="email" id="email" class="login-input" v-model="email">
      </div>

      <div class="form-control mb-more">
        <label for="password">Password</label>
        <input type="password" name="password" id="password" class="login-input" v-model="password">
      </div>

      <div class="form-control">
        <input type="submit" class="btn-submit" value="Create Account"/>
      </div>

    </form>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      password: '',
    }
  },
  methods: {
    register() {
      this.$store.dispatch('register', {
        name: this.name,
        email: this.email,
        password: this.password,
      })
        .then(response => {
          this.$router.push({ name: 'login' })
        })
    }
  }
}
</script>