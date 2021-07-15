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
      </div>
      <div class="user-action-group">
        <i class="bi bi-search"/>
        <i class="bi bi-translate"/>
        <i class="bi bi-cart3"/>
        <i class="bi bi-person-fill"/>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'SignIn',
  data() {
    return {
      webLogo: require('@/assets/logo.png')
    }
  }
}
</script>

<style scoped lang="scss">
.running-message {
  height: 40px;
  display: flex;
  color: #ffffff;
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
  height: 88px;
  box-shadow: 1px 2px 3px rgb(0 0 0 / 20%);
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
    justify-content: center;
  }
  .user-action-group {
    display: flex;
    flex-direction: row;
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
