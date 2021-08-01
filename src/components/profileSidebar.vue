<template>
    <div
        class="w-96 bg-white border-brand border-1 rounded mt-6"
      >
        <div :class="{'invisible': hidden}" class="text-right p-3 text-xs">
          <button @click="hideSidebar()" class="text-brand poppins-font">Hide</button>
        </div>
        <div class="text-center pb-8 px-8">
          <img
            class="w-24 h-24 inline-block"
            src="@/assets/img/tim_mcbaj_53652000_2255623191378916_4966133143083590398_n.png"
            alt=""
          />
          <h4 class="text-2xl font-semibold mt-3 mb-1 poppins-font">
            Ekemini Mark
          </h4>
          <p class="text-xs leading-5 poppins-font">
            I’m a wedding and portrait photographer based in Lagos, Nigeria.
            I’ve been shooting weddings since I was in high school (before I
            ever had my driver’s license!).
          </p>
          <div class="flex my-5">
            <div class="poppins-font flex-1">
              <h4 class="text-xl font-bold m-0">22.1k</h4>
              <p class="text-xs m-0 text-gray-500">Total Views</p>
            </div>
            <div class="poppins-font flex-1">
              <h4 class="text-xl font-bold m-0">
                <img
                  class="w-5 mx-1 inline-block"
                  src="@/assets/img/heart-outline.png"
                />13.1k
              </h4>
              <p class="text-xs m-0 text-gray-500">Total Likes</p>
            </div>
            <div class="poppins-font flex-1">
              <h4 class="text-xl font-bold m-0">Sony 92J</h4>
              <p class="text-xs m-0 text-gray-500">Camera Lens</p>
            </div>
          </div>
          <ul class="flex breadcrumbs bulleted poppins-font text-xs my-2">
            <li>Category</li>
            <li>Food</li>
            <li>Portrait</li>
            <li>Wedding</li>
            <li>Model</li>
          </ul>
          <ul class="flex breadcrumbs poppins-font text-xs my-2">
            <li class="fix">Location</li>
            <li>Lagos, Nigeria</li>
          </ul>
          <div class="flex justify-center items-center mb-2 mt-8">
            <img
              class="h-7 w-7 mr-1"
              src="@/assets/img/logo-share.png"
              alt=""
            /><a href="#" class="poppins-font text-sm flex-initial"
              >www.peexoo.ai/anijohnson</a
            >
          </div>
          <div class="flex my-7 justify-center items-center">
            <button class="icon-button flex-initial">
              <img class="h-4 w-4" src="@/assets/img/logo-twitter.png" alt="" />
            </button>
            <button class="icon-button flex-initial">
              <img
                class="h-4 w-4"
                src="@/assets/img/logo-instagram.png"
                alt=""
              />
            </button>
            <button class="icon-button flex-initial">
              <img class="h-4 w-4" src="@/assets/img/logo-letter.png" alt="" />
            </button>
            <a
              href=""
              class="
                px-4
                py-2
                rounded-full
                mx-1
                bg-brand
                poppins-font
                text-white text-sm
              "
              >Book Now</a
            >
          </div>
          <div
            class="
              text-center
              flex
              justify-center
              brand-gray
              items-center
              text-xs
              poppins-font
            "
          >
            <span class="flex-initial poppins-font">Built</span>
            <img
              class="h-5 w-5 mx-1"
              src="@/assets/img/logo-heart-filled.png"
              alt=""
            />
            <span href="#" class="flex-initial poppins-font"> on peexoo </span>
          </div>
        </div>
      </div>
</template>

<script>
export default {
  data () {
    return {
      hidden: this.dismissable
    }
  },
  props: {
    dismissable: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    hideSidebar () {
      this.$emit('on-hidden')
    }
  }
}
</script>
