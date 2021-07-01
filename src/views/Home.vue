<template>
    <main class="main">
        <div class="container">
            <Slider />
            <SwiperSlider>
              <template v-slot:title>
                موبایل
              </template>
              <a href="product.html" class="swiper-slide" v-for="item in 6" :key="item">
                    <div class="slider__box">
                        <div class="slider__image"><img :src="require(`../assets/img/slider/${item}.jpg`)" alt="" class="slider__img"></div>
                        <div class="slider__title2">
                            گوشی موبایل سامسونگ مدل نوت 20
                        </div>
                        <div class="slider__price">
                            <span class="slider__compare-price">12,200,000</span>
                            <span class="slider__total-price">12,400,000 تومان</span>
                        </div>
                        <span class="slider__discount">%6</span>
                    </div>
                </a>
            </SwiperSlider>
            <SwiperSlider>
              <template v-slot:title>
                لب تاپ
              </template>
              <a href="product.html" class="swiper-slide" v-for="item in 4" :key="item">
                    <div class="slider__box">
                        <div class="slider__image"><img :src="require(`../assets/img/slider/${item}.jpg`)" alt="" class="slider__img"></div>
                        <div class="slider__title2">
                            گوشی موبایل سامسونگ مدل نوت 20
                        </div>
                        <div class="slider__price">
                            <span class="slider__compare-price">12,200,000</span>
                            <span class="slider__total-price">12,400,000 تومان</span>
                        </div>
                        <span class="slider__discount">%6</span>
                    </div>
                </a>
            </SwiperSlider>
        </div>
    </main>
</template>

<script>
import Slider from '../components/Slider.vue';
import SwiperSlider from '../components/SwiperSlider'
export default {
  name: "Home",

  components: {
    SwiperSlider,
    Slider
  },

 
}
</script>
