<template>
  <AuthNavBar/>
  <div class="content-wrapper">
    <div id="carouselHead" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-inner">
        <div class="carousel-item active">
          <div class="overlay-content">
            <img :src="slideshowContentLogo" alt="Content Logo">
            <b>From The Harbour To Your Home</b>
            <p>A New Way to Enjoy Quality Seafood at Home</p>
            <button>Shop Now</button>
          </div>
          <img class="d-block w-100" :src="slideshow.slideshow01" alt="Slideshow 1">
        </div>
        <div class="carousel-item">
          <div class="overlay-content">
            <img :src="slideshowContentLogo" alt="Content Logo">
            <b>From The Harbour To Your Home</b>
            <p>A New Way to Enjoy Quality Seafood at Home</p>
            <button>Shop Now</button>
          </div>
          <img class="d-block w-100" :src="slideshow.slideshow01" alt="Slideshow 1">
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselHead" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselHead" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
    <div class="offer-card">
      <div class="inner-container">
        <b>15% off for your first order</b>
        <i class="bi bi-x-square"/>
      </div>
    </div>
    <div class="content-tile">
      <div class="inner-container">
        <div class="tile-row">
          <div class="tile-image" v-bind:style="{backgroundImage: 'url('+contentTile1+')'}"/>
          <div class="tile-desc">
            <b>Seafood</b>
            <p>Our simple grilled fish made us famous, and that’s just a fraction of our menu. Find a familiar favorite, or let one of our “menu masters” offer recommendations based on your preferences for flavor, preparation and pairing.</p>
            <button>Shop Now</button>
          </div>
        </div>
        <div class="tile-row">
          <div class="tile-desc">
            <b>Retail Market</b>
            <p>Every one of our restaurants has a retail market showcasing the seafood we serve on our menu. Order any menu item to go, shop for fresh fish to prepare at home, or grab a box of ready-to-eat smoked salmon.</p>
            <button>Shop Now</button>
          </div>
          <div class="tile-image" v-bind:style="{backgroundImage: 'url('+contentTile2+')'}"/>
        </div>
      </div>
    </div>
    <div class="customer-favorite">
      <div class="header">
        <i class="bi bi-heart"/>
        <b>Customer Favourite</b>
      </div>
      <div class="favorite-content" v-bind:style="{backgroundImage: 'url('+contentTile1+')'}">
        <button>Show More</button>
      </div>
    </div>
    <div class="customer-feedback">
      <div class="feedback-header">
        <b>What others are saying</b>
        <p>We’ll also keep you updated on our seasonal produce and exciting upcoming events.</p>
      </div>
      <div class="inner-container">
        <div class="row">
          <div class="testimony-box col-lg-4">
            <div class="box">
              <i class="bi bi-person-circle"/>
              <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc accumsan augue id aliquet fermentum. Cras ac elementum velit.</p>
            </div>
          </div>
          <div class="testimony-box col-lg-4">
            <div class="box">
              <i class="bi bi-person-circle"/>
              <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc accumsan augue id aliquet fermentum. Cras ac elementum velit.</p>
            </div>
          </div>
          <div class="testimony-box col-lg-4">
            <div class="box">
              <i class="bi bi-person-circle"/>
              <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc accumsan augue id aliquet fermentum. Cras ac elementum velit.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <footer>
      <div class="inner-container">
        <div class="row">
          <div class="col-lg-4">
            <b>Quick links</b>
            <p>FAQ</p>
            <p>Business inquiries</p>
            <p>Terms of service</p>
            <p>Refund & Policy</p>
          </div>
          <div class="col-lg-4">
            <b>Powered by</b>
            <p>PT. Ruangan Pendingi Indonesia</p>
            <b class="margin-top">Supplied by</b>
            <p>PT. Ruangan Pendingi Indonesia</p>
          </div>
          <div class="col-lg-4">
            <b>Newsletter</b>
          </div>
        </div>
        <b class="footer-text">Copyright Reserved © 2021. Fishop Indonesia.</b>
      </div>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import AuthNavBar from '@/components/AuthNavBar';

export default {
  name: 'Home',
  components: {AuthNavBar},
  data() {
    return {
      contentTile1: require('@/assets/content-tile-1.jpg'),
      contentTile2: require('@/assets/content-tile-2.jpg'),
      slideshowContentLogo: require('@/assets/slideshow-content-logo.png'),
      slideshow: {
        slideshow01: require('@/assets/slideshow-01.jpg')
      },
      products: [
        {id: 1, label: 'Ikan Goreng', price: 150000, image: require('@/assets/ikan.jpeg')},
        {id: 2, label: 'Ikan Goreng', price: 150000, image: require('@/assets/ikan.jpeg')},
        {id: 3, label: 'Ikan Goreng', price: 150000, image: require('@/assets/ikan.jpeg')},
        {id: 4, label: 'Ikan Goreng', price: 150000, image: require('@/assets/ikan.jpeg')},
        {id: 5, label: 'Ikan Goreng', price: 150000, image: require('@/assets/ikan.jpeg')},
        {id: 6, label: 'Ikan Goreng', price: 150000, image: require('@/assets/ikan.jpeg')},
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.content-wrapper {
  top: 40px;
  position: absolute;
}
.carousel .carousel-item {
  position: relative;
  .overlay-content {
    width: 50%;
    height: 100%;
    display: flex;
    position: absolute;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    img {
      width: 28rem;
      margin-top: 4rem;
    }
    b, p {
      color: white;
      display: block;
      font-size: 1rem;
    }
    button {
      height: 48px;
      width: 128px;
      border: none;
      color: white;
      outline: none;
      font-weight: bold;
      border-radius: 24px;
      background-color: #FF5757;
    }
  }
}
.offer-card {
  height: 96px;
  position: relative;
  background-color: rgba(163, 185, 228, 0.47);
  .inner-container {
    height: 100%;
    margin: auto;
    display: flex;
    padding: 0 32px;
    max-width: 1984px;
    align-items: center;
    justify-content: flex-end;
    b {
      flex: 1;
      color: #2F57A6;
      font-size: 28px;
    }
    i {
      color: #3560B3;
      cursor: pointer;
      font-size: 24px;
      position: absolute;
    }
  }
}
.content-tile {
  display: flex;
  justify-content: center;
  .inner-container {
    max-width: 1920px;
    .tile-row {
      height: 32rem;
      display: flex;
      flex-direction: row;
      .tile-image {
        width: 50%;
        background-size: cover;
      }
      .tile-desc {
        width: 50%;
        display: flex;
        padding: 28px;
        align-items: center;
        flex-direction: column;
        justify-content: center;
        b {
          color: #2F57A6;
          font-size: 24px;
          margin-bottom: 8px;
        }
        p {
          color: #3560B2;
          font-size: 20px;
          margin-bottom: 16px;
        }
        button {
          height: 48px;
          width: 128px;
          border: none;
          color: white;
          outline: none;
          font-weight: bold;
          border-radius: 24px;
          background-color: #FF5757;
        }
      }
      @media screen and (min-width: 1440px) {
        & {
          height: 40rem;
        }
      }
    }
  }
}
.customer-favorite {
  .header {
    width: 100%;
    height: 96px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    i {
      color: #2F57A6;
      font-size: 24px;
    }
    b {
      margin: 0;
      color: #2F57A6;
      font-size: 20px;
    }
  }
  .favorite-content {
    height: 192px;
    display: flex;
    padding: 24px 0;
    align-items: center;
    background-size: cover;
    flex-direction: column;
    justify-content: flex-end;
    button {
      height: 48px;
      width: 128px;
      border: none;
      color: white;
      outline: none;
      font-weight: bold;
      border-radius: 24px;
      background-color: #FF5757;
    }
  }
}
.customer-feedback {
  display: flex;
  align-items: center;
  flex-direction: column;
  .feedback-header {
    width: 100%;
    height: 80px;
    display: flex;
    padding: 0 32px;
    flex-direction: column;
    justify-content: center;
    background-color: rgba(163, 185, 228, 0.47);
    b {
      color: #2F57A6;
      font-size: 20px;
    }
    p {
      margin: 0;
      color: #3560B2;
      font-size: 16px;
    }
  }
  .inner-container {
    width: 100%;
    height: 100%;
    padding: 0 32px;
    max-width: 1088px;
    .row {
      .testimony-box {
        display: flex;
        justify-content: center;
        .box {
          width: 256px;
          height: 256px;
          display: flex;
          align-items: center;
          flex-direction: column;
          justify-content: center;
          p {
            margin: 0;
            color: #3560B2;
            font-size: 16px;
          }
          i {
            color: #2F57A6;
            font-size: 40px;
          }
        }
      }
    }
  }
}
footer {
  display: flex;
  padding: 32px 0;
  justify-content: center;
  background-color: rgba(163, 185, 228, 0.47);
  .inner-container {
    width: 100%;
    height: 100%;
    padding: 0 32px;
    max-width: 1088px;
    .row div {
      display: flex;
      flex-direction: column;
      b, p {
        font-size: 16px;
        text-align: left;
        @media screen and (max-width: 768px) {
          & {
            text-align: center;
          }
        }
      }
      b {
        color: #2F57A6;
        margin-bottom: 8px;
      }
      p {
        color: #3560B2;
        cursor: pointer;
        margin-bottom: 4px;
      }
      .margin-top {
        margin-top: 8px;
      }
    }
    .footer-text {
      color: #2F57A6;
      display: block;
      margin: 16px 0 0;
    }
  }
}
</style>
