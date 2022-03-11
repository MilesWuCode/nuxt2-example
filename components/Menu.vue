<template>
  <div>
    <router-link to="/">Index</router-link>
    <router-link to="/login">Login</router-link>
    <router-link to="/profile">Profile</router-link>
    <router-link to="/guest">Guest</router-link>
    <router-link to="/public">Public</router-link>
    <Logout />

    <div>{{ $auth.loggedIn }}</div>
  </div>
</template>

<script>
export default {
  name: 'MenuComponent',
}
</script>
