<template>
  <div class="py-4 swipper-section">
    <div ref="carousel" v-swiper:mySwiper="swiperOption">
      <div class="swiper-btn-icon left" @click="goPrev()">
        <!-- <img src="~assets/img/swiper-left.svg" alt=""> -->
      </div>

      <div class="swiper-wrapper">
        <div class="swiper-slide px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-1.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-2.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-3.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-4.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-5.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-6.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-7.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-8.png"
            >
        </div>
        <div class="swiper-slide rounded-md px-2">
            <img
              class="w-full"
              src="@/assets/img/thumb-9.png"
            >
        </div>
      </div>

      <div class="swiper-btn-icon right" @click="goNext()">
        <!-- <img src="~assets/img/swiper-right.svg" alt=""> -->
      </div>
      <div class="swiper-pagination swiper-pagination-bullets" />
    </div>
  </div>
</template>

<script>
import '@/assets/swiper.css'
export default {
  props: {
    itemsPerView: {
      type: Number,
      default: 12
    }
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        slidesPerView: this.itemsPerView,
        breakpoints: {
          // when window width is >= 320px
          320: {
            slidesPerView: 2
          },
          // when window width is >= 480px
          480: {
            slidesPerView: 3
          },
          // when window width is >= 640px
          640: {
            slidesPerView: 4
          },
          // when window width is >= 640px
          1024: {
            slidesPerView: this.itemsPerView
          }
        }
      },
      products: [
        { imageUrl: 'thumb-1.png' },
        { imageUrl: 'thumb-2.png' },
        { imageUrl: 'thumb-3.png' },
        { imageUrl: 'thumb-4.png' },
        { imageUrl: 'thumb-5.png' },
        { imageUrl: 'thumb-6.png' },
        { imageUrl: 'thumb-7.png' },
        { imageUrl: 'thumb-8.png' },
        { imageUrl: 'thumb-9.png' }
      ]
    }
  },
  computed: {
    swiper () {
      return this.$refs.carousel.swiper
    }
  },
  methods: {
    goNext () {
      return this.swiper.slideNext()
    },
    goPrev () {
      return this.swiper.slidePrev()
    },
    gotoProduct (itemId, slug) {
      alert('clicked')
      this.$router.push({
        name: 'store_slug-items-id',
        params: {
          id: itemId,
          store_slug: slug
        }
      })
    }
  }
}
</script>

<style scoped>
.swiper-slide.active, .swiper-slide:hover {
  border: 1px solid #f09e28;
  cursor: pointer;
}
.swipper-section {
  position: relative;
}
.swipper-section .swiper-slide img {
  border-radius: 8px;
}
.swiper-btn-icon {
  position: absolute !important;
  width: 20px;
  /* background: orange; */
  top: calc(50% - 10px);
  z-index: 22;
  cursor: pointer;
}
.swiper-btn-icon.left {
  left: -5px;
  text-align: left;
}
.swiper-btn-icon.right {
  right: -5px;
  text-align: right;
}

</style>
