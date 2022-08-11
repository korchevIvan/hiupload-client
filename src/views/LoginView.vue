<template>
  <div>
    <form action="" @submit.prevent="login">
      <button type="submit">Login</button>
    </form>
  </div>
</template>

<script>
import {mapActions} from 'vuex'

export default {
  methods: {
    ...mapActions({
      loginAction: 'auth/login'
    }),
    login() {
      this.loginAction({email: 'unbsold@yandex.ru', password: '12345678'})
    }
  }
}
</script>
