<template>
  <AuthNavBar/>
  <div class="content">
    <div class="auth-form">
      <h1>Sign In</h1>
      <input type="text" v-model="username" placeholder="Username">
      <input type="password" v-model="password" placeholder="Password">
      <button @click="onClickSignIn" :disabled="fetchLoading">
        Sign In
      </button>
      <p>OR</p>
      <router-link to="/signup" replace>Sign Up</router-link>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import AuthNavBar from '@/components/AuthNavBar';

export default {
  name: 'SignIn',
  components: {AuthNavBar},
  data() {
    return {
      username: '',
      password: '',
      fetchLoading: false
    }
  },
  methods: {
    async onClickSignIn() {
      try {
        this.fetchLoading = true;
        await axios({
          method: 'post',
          url: 'https://foreatapi.herokuapp.com/api/auth/login',
          data: {
            username: this.username,
            password: this.password
          }
        });
        document.cookie = 'auth=true';
        await this.$router.replace('/');
      } catch (e) {
        console.error(e);
      } finally {
        this.fetchLoading = false;
      }
    }
  }
}
</script>

<style scoped lang="scss">
.content {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  .auth-form {
    width: 85%;
    max-width: 425px;
    h1 {
      color: #2B5493;
      font-weight: bold;
    }
    input {
      width: 100%;
      border: none;
      outline: none;
      display: block;
      padding: 12px 0;
      font-size: 20px;
      margin-bottom: 12px;
      border-bottom: 1px solid #000000;
    }
    p {
      margin: 16px 0;
    }
    a {
      color: black;
      font-weight: bold;
    }
    button {
      width: 96px;
      height: 48px;
      border: none;
      outline: none;
      color: #ffffff;
      font-size: 16px;
      margin-top: 8px;
      font-weight: bold;
      border-radius: 24px;
      background-color: #f66363;
      &:disabled {
        background-color: darkgrey;
      }
    }
  }
}
</style>
