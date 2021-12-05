<template>
    <div id="login">
        <div class="login-card">

            <div class="card-title">
                <h1> WELCOME! </h1>
            </div>

            <div class="content">
                <form method="POST" action="">
                    <input id="email" type="email" v-model="email" placeholder="Email" required>
                    <input id="password" type="password" v-model="password" minlength="6" placeholder="Password" required>
                    <div class="level options">
                        <router-link class="btn btn-link level-right" to="/forgetpassword">Forgot Password? </router-link>
                    </div>
                    <button type="button" class="button is-dark is-large is-fullwidth has-text-centered">Login</button><br>
                     <div class="has-text-centered">
                        <div class=".has-margin-top-5"> Don't have an account? </div>
                        <div> Click <router-link to="/register"> here </router-link> to register</div> 
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data(){
        return {
            email: '',
            password: '',
            error: ''
        }
    },
    methods: {
        login(){
            try {
                Login(this.email, this.password);
                this.$router.push('/');
            } catch (error) {
                this.error = error;
            }
        }
    }
}
</script>

<style>

</style>