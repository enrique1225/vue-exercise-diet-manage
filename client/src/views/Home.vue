<template>
  <section class="hero is-info is-fullheight has-back-img">

      <div class="hero-body">
        <div class="container has-text-centered">
          <div class="column is-6 is-offset-3">
            <h1 class="title has-text-black is-size-1">
                {{ title }}
            </h1>
            <h1 class="subtitle has-text-black is-size-2">
                {{ subtitle }}
            </h1>
            <div class="is-centered">
              <router-link to="/register"> <button class="button is-success"> Register </button> </router-link>
            </div>
          </div>

        </div>
      </div>
    </section>
</template>

<script>
  export default {
    data: function() {
      return {
        'title': 'Welcome to GET FIT',
        'subtitle': 'Join Us TODAY!',
      }
    }
  }
</script>

<style scoped>

.has-back-img {
  background: url('../assets/img/yoga-and-zumba.jpg')center center;
  background-size: cover;
}

</style>

