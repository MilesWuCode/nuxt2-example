<template>
  <div>
    <h1>Profile</h1>
    auth:{{ $auth.user }}
    <hr />
    <!-- api:{{ user }} -->
    <hr />
    <button @click="getUser">Get User</button>
    get:{{ getUserData }}
    <hr />
    <button @click="fetchUser">Fetch User</button>
    get:{{ fetchUserData }}
  </div>
</template>

<script>
export default {
  name: 'ProfilePage',
  auth: true,
  async asyncData({ $axios }) {
    const user = await $axios.$get('/api/user')
    console.log(user)
    return { user }
  },
  data() {
    return {
      getUserData: {},
      fetchUserData: {},
    }
  },
  methods: {
    async getUser() {
      this.getUserData = await this.$axios.$get('/api/user')
    },
    async fetchUser() {
      this.fetchUserData = await this.$auth.fetchUser()
    },
  },
}
</script>
