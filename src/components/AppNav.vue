<template>
  <header class="flex flex-wrap md:flex-no-wrap items-center justify-between mb-6 -mx-3 -mt-3">
    <ul class="flex items-center">
      <li>
        <router-link :to="{name: 'home'}" class="text-sm inline-block p-3 text-gray-800">Home</router-link>
      </li>
      <li>
        <router-link :to="{ name: 'uploads' }" class="text-sm inline-block p-3 text-gray-800">Your files</router-link>
      </li>
    </ul>
    <ul class="flex items-center">
      <template v-if="!authenticated">
        <li>
          <router-link :to="{name: 'login'}" class="text-sm inline-block p-3 text-gray-800">Sign In</router-link>
        </li>
        <li>
          <a href="" class="text-sm inline-block p-3 text-gray-800">Create account</a>
        </li>
      </template>
      <template v-else>
        <li>
          <a href="" class="text-sm inline-block p-3 text-gray-800">Account</a>
        </li>
        <li>
          <a href="#" class="text-sm inline-block p-3 text-gray-800" @click.prevent="logout">Log out</a>
        </li>
      </template>
    </ul>
  </header>
</template>

<script>
import {mapGetters, mapActions} from 'vuex'
export default {
  computed: {
    ...mapGetters({
      authenticated: "auth/authenticated",
      user: "auth/user",
    })
  },

  methods: {
    ...mapActions({
      logoutActions: 'auth/logout'
    }),
    async logout() {
      await this.logoutActions()
      this.$router.replace({'name': 'home'})
    }
  }
}
</script>