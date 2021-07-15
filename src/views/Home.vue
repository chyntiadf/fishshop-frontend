<template>
  <div id="content">
    <h2 class="lineClass"><span class="lineSpanClass">PRODUK KAMI</span></h2>
    <ul id="responsive" class="product-container">
      <li v-for="(item) in products" class="item-container" :key="item.id">
        <img :src="item.image" alt="product"/>
        <h3>{{item.message}}</h3>
      </li>
    </ul>

<!--    <div class="flex-container">-->
<!--      <div><a href="../html/product.html"><img src="../img/fishop_banner_1.png" alt="shop_make_up.jpg"></a></div>-->
<!--      <div><a href="../html/product.html"><img src="../img/fishop_banner_2.png" alt="shop_skincare.jpg"></a></div>-->
<!--    </div>-->

<!--    <h2 class="lineClass"><span class="lineSpanClass">KATA MEREKA</span></h2>-->
<!--    <ul id="responsive2" style="margin-top: 20px;">-->
<!--      <li>-->
<!--        <p class="img-text" style="text-align: center;"><b>Yati (35)</b> <br>Ibu Rumah Tangga</p>-->
<!--        <p class="img-text" style="text-align: center;"><b>"</b> Ikannya segar, fresh dan berkualitas! <br> Mau beli lagi disini. <b>"</b></p>-->
<!--      </li>-->
<!--      <li>-->
<!--        <p class="img-text" style="text-align: center;"><b>Rizki (21)</b> <br>Mahasiswa</p>-->
<!--        <p class="img-text" style="text-align: center;"><b>"</b> Bisa ngirit uang jajan! Soalnya murah banget! Suka promo! ya namanya-->
<!--          juga mahasiswa <b>"</b></p>-->
<!--      </li>-->
<!--      <li>-->
<!--        <p class="img-text" style="text-align: center;"><b>Dinda (12)</b> <br>Pelajar</p>-->
<!--        <p class="img-text" style="text-align: center;"><b>"</b> Mama suka banget beli disini!-->
<!--          Aku yang pesen, yang jual baik banget! Enak banget belanja disini! <b>"</b></p>-->
<!--      </li>-->
<!--      <li>-->
<!--        <p class="img-text" style="text-align: center;"><b>Abang (40)</b> <br>Pengusaha</p>-->
<!--        <p class="img-text" style="text-align: center;"><b>"</b> Lagi covid gini, ke pasar nemenin istri tuh jadi takut, untung ada Fishop.-->
<!--          Jadi ada alesan buat gak ke pasar! <b>"</b></p>-->
<!--      </li>-->
<!--    </ul>-->
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

const {$} = window;

$(document).ready(function() {
  $('#responsive').lightSlider({
    item: 4,
    speed: 600,
    loop: false,
    slideMove: 2,
    easing: 'cubic-bezier(0.25, 0, 0.25, 1)',
    responsive : [
      {
        breakpoint:800,
        settings: {
          item:3,
          slideMove:1,
          slideMargin:6,
        }
      },
      {
        breakpoint:480,
        settings: {
          item:2,
          slideMove:1
        }
      }
    ]
  });
});

export default {
  name: 'Home',
  components: {
  },
  data() {
    return {
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
.product-container {
  li {
    display: flex;
    justify-content: center;
    img {
      width: 80%;
    }
  }
}
</style>
