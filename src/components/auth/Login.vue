<template>
    <div class="flex-center">
        <div class="login-form">
            <h2 class="login-heading">Login</h2>
            <form action="#" @submit.prevent="login">
                <div class="form-control">
                    <label for="email">Email</label>
                    <input type="email" v-model="username" name="username" id="username" class="login-input">
                </div>
                <div class="form-control mb-more">
                    <label for="password">Password</label>
                    <input type="password" v-model="password" name="password" id="password" class="login-input">
                </div>
                <div class="form-control">
                    <input type="submit" class="btn-submit" value="Login">
                </div>
            </form>
        </div>
    </div>    
</template>
<script>
export default {
    name: 'login',
    data() {
        return {
            username: '',
            password: '',
        }
    },
    methods: {
        login() {
            this.$store.dispatch('retrieveToken', {
                username: this.username,
                password: this.password,
            })
            .then(response => {
                this.$router.push({ name: 'todo' })
            })
        }
    }
}
</script>




