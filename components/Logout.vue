<template>
  <a href="javascript:;" @click="onClick">Logout</a>
</template>

<script>
export default {
  name: 'LogoutComponent',
  methods: {
    async onClick() {
      await this.$auth.logout()
    },
  },
}
</script>
