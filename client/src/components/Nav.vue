<template>
<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item">
      <router-link to="/"> <img class="logo" src="../assets/img/logo02.png"> </router-link>
    </a>

    <a :class="{ 'is-active':isOpen }" @click="isOpen = !isOpen" role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false" >
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>

  <div :class="{ 'is-active':isOpen }" class="navbar-menu">
    <div class="navbar-start">
      <a v-for="navLeftItem in navLeftItems" class="navbar-item" v-bind:href="navLeftItem.route" :key="navLeftItem.id">
        {{ navLeftItem.item }}
      </a>
    </div>

    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <router-link class="button is-dark is-fullwidth has-text-centered" to="/login">
            Log in
          </router-link>
        </div>
      </div>
    </div>
  </div>
</nav>
</template>

<script>
import LoginModal from "../views/Login"
export default {
  components: {
    LoginModal
  },
  data() {
    // isOpen: false,
    return {
        active: false,
        isOpen: false,
        navLeftItems: [{
            "item": "Home",
            "route": "/"
          },
          {
            "item": "About Us",
            "route": "/aboutus"
          },
          {
            "item": "Activities",
            "route": "/activities"
          },
          {
            "item": "Contact",
            "route": "/contact"
          }],  
          components: {
            LoginModal
        },
        methods: {
          openLogin() {
            this.$modal.open({
                parent: this,
                component: LoginModal,
                hasModalCArd: true,
                props: {
                }
            })
          },
      }  
    }
  },
}
</script>

<style>
  .is-current {
    font-weight: bold;
    color: blueviolet
  }
  .logo{
    width: 100px;
    height: 50px;
    max-height: none!important;
  }
</style>