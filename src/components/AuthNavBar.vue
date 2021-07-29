<template>
  <div class="running-message">
    <b>GRATIS ONGKOS KIRIM</b>
    <p>DENGAN MINIMUM PEMBELIAN Rp.150.000</p>
  </div>
  <nav class="navbar navbar-expand-lg navbar-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">
        <img :src="webLogo" alt="Logo" height="24"/>
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle active" href="#" id="navbarDropdownProduct" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Product
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdownProduct">
              <li><a class="dropdown-item" href="#">Sample</a></li>
            </ul>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle active" href="#" id="navbarDropdownJournal" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Journal
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdownJournal">
              <li><a class="dropdown-item" href="#">Sample</a></li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Fishop-Go</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">About Us</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Customer Care</a>
          </li>
        </ul>
        <div class="user-action-group">
          <i class="bi bi-search"/>
          <i class="bi bi-translate"/>
          <i class="bi bi-cart3"/>
          <div v-if="authCookie" class="dropdown-container">
            <i class="bi bi-person-fill"/>
            <div class="custom-dropdown-outer">
              <div class="custom-dropdown-inner">
                <p @click="signOutUser">Sign Out</p>
              </div>
            </div>
          </div>
          <i v-else class="bi bi-person-fill" @click="navigateToauth"/>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
const authCookie = document.cookie.match('auth=true');

export default {
  name: 'SignIn',
  data() {
    return {
      authCookie: authCookie && authCookie.length > 0,
      webLogo: require('@/assets/logo.png')
    }
  },
  methods: {
    navigateToauth() {
      this.$router.push('/signin');
    },
    signOutUser() {
      document.cookie = "auth=true; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";
      window.location.reload();
    }
  }
}
</script>

<style scoped lang="scss">
.running-message {
  z-index: 1;
  height: 40px;
  display: flex;
  color: #ffffff;
  position: relative;
  align-items: center;
  justify-content: center;
  background-color: #f66363;
  @media screen and (max-width: 425px) {
    & {
      height: 56px;
      flex-direction: column;
    }
  }
  p {
    margin: 0 0 0 8px;
  }
}
.navbar {
  z-index: 2;
  height: 88px;
  position: relative;
  backdrop-filter: blur(8px);
  box-shadow: 1px 2px 3px rgb(0 0 0 / 20%);
  background-color: rgba(255, 254, 249, 0.5);
  .container-fluid {
    padding: 0 24px;
  }
  @media screen and (max-width: 768px) {
    & {
      height: auto;
    }
  }
  .navbar-toggler span {
    color: #000000;
  }
  .navbar-collapse {
    position: relative;
    justify-content: center;
    @media screen and (min-width: 769px) {
      ul {
        margin-left: -8rem;
        .dropdown-menu {
          margin-left: 0;
        }
      }
    }
  }
  .user-action-group {
    right: 0;
    display: flex;
    position: absolute;
    flex-direction: row;
    .dropdown-container {
      position: relative;
      i {
        border-radius: 100%;
        background-color: #f66363;
      }
      .custom-dropdown-outer {
        right: 0;
        display: none;
        position: absolute;
        .custom-dropdown-inner {
          width: 128px;
          height: 40px;
          display: flex;
          margin-top: 8px;
          border-radius: 4px;
          align-items: center;
          justify-content: center;
          background-color: white;
          p {
            margin: 0;
            width: 100%;
            cursor: pointer;
          }
        }
      }
      &:hover {
        .custom-dropdown-outer {
          display: flex;
        }
      }
    }
    @media screen and (max-width: 768px){
      & {
        margin-top: 8px;
        position: relative;
        justify-content: center;
      }
    }
    i {
      width: 32px;
      height: 32px;
      display: block;
      font-size: 20px;
      cursor: pointer;
      margin-left: 2px;
      &:last-child {
        border-radius: 100%;
        background-color: #f66363;
      }
    }
  }
}
</style>
