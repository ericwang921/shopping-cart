<template>
  <div id="login" class="box has-text-centered">
    <h2 class="title">Fullstack Clothing</h2>
    <button @click="login"
      :class="[{'is-loading': loading}, 'button is-primary']">
      Login
    </button>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';

export default {
  name: 'LoginBox',
  computed: {
    ...mapGetters({
      loading: 'login/loading'
    }),
  },
  methods: {
    login() {
      this.$store.dispatch("login/login").then(() => {
        this.$router.push({ path: '/products' });
      });
    }
  }
}
</script>

<style scoped>
.box {
  padding: 30px;
}
</style>
