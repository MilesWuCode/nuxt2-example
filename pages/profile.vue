<template>
  <div>
    <h1>Profile</h1>
    auth:{{ $auth.user }}
    <hr />
    api:{{ user }}
    <hr />
    <button @click="getUser">Get User</button>
    get:{{ getUserData }}
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
    }
  },
  methods: {
    async getUser() {
      this.getUserData = await this.$axios.$get('/api/user')
    },
  },
}
</script>
