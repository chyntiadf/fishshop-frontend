<template>
  <AuthNavBar/>
  <div class="content">
    <div class="auth-form">
      <h1>Sign Up</h1>
      <input type="text" v-model="email" placeholder="Email">
      <input type="text" v-model="username" placeholder="Username">
      <input type="password" v-model="password" placeholder="Password">
      <input type="number" v-model="phone" placeholder="Phone">
      <textarea placeholder="Address" v-model="address"/>
      <button @click="onClickSignUp">
        Sign Up
      </button>
      <p>OR</p>
      <router-link to="/signin" replace>Sign In</router-link>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import AuthNavBar from '@/components/AuthNavBar';

export default {
  name: 'SignUp',
  components: {AuthNavBar},
  data() {
    return {
      email: '',
      username: '',
      password: '',
      phone: '',
      address: ''
    }
  },
  methods: {
    async onClickSignUp() {
      try {
        await axios({
          method: 'post',
          url: 'https://foreatapi.herokuapp.com/api/auth/register',
          data: {
            email: this.email,
            username: this.username,
            password: this.password,
            phone: this.phone,
            address: this.address,
            fullname: this.username,
            countryid: 'Indonesia',
            provinceid: 'DKI Jakarta',
            cityid: 'Jakarta Utara',
            profilepic: 'https://via.placeholder.com/250'
          }
        });
        await this.$router.replace('/signin');
      } catch (e) {
        console.error(e);
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
      &::-webkit-outer-spin-button,
      &::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
      }
      &[type=number] {
        -moz-appearance: textfield;
      }
    }
    textarea {
      width: 100%;
      border: none;
      outline: none;
      display: block;
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
    }
  }
}
</style>
