<template>
  <div>
    <h1>Login</h1>
    <form @submit.prevent="userLogin">
      <div>
        <label>Username</label>
        <input v-model="login.username" type="text" />
      </div>
      <div>
        <label>Password</label>
        <input v-model="login.password" type="text" />
      </div>
      <div>
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
    return {
      login: {
        username: 'miles@email.com',
        client_id: 2,
        client_secret: 'LUGGsbSZnOoU6od1Mq8xwC8deNvxwA8eSobONbTH',
        password: 'password',
        grant_type: 'password',
        scope: '*',
      },
    }
  },
  methods: {
    async userLogin() {
      const response = await this.$auth.loginWith('local', { data: this.login })
      console.log(response)
    },
  },
}
</script>
