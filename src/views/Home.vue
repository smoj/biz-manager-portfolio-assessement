<template>
  <div>
    <div class="rounded-md bg-gray-600 h-32 mx-3 banner-image">.</div>
    <div class="flex mx-10">
      <div class="w-1/3 bg-white border-brand border-1 rounded -mt-24">
        <div class="text-right p-3 text-xs">
          <button class="text-brand poppins-font">Hide</button>
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
                <img class="h-4 w-4 mx-1 inline-block" src="https://via.placeholder.com/150x50" />13.1k
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
              class="h-4 w-4 mr-2"
              src="https://via.placeholder.com/150x50"
              alt=""
            /><a href="#" class="poppins-font text-sm flex-initial"
              >www.peexoo.ai/anijohnson</a
            >
          </div>
          <div class="flex my-7 justify-center items-center">
            <button class="icon-button flex-initial">
              <img
                class="h-4 w-4"
                src="https://via.placeholder.com/150x50/000000"
                alt=""
              />
            </button>
            <button class="icon-button flex-initial">
              <img
                class="h-4 w-4"
                src="https://via.placeholder.com/150x50/000000"
                alt=""
              />
            </button>
            <button class="icon-button flex-initial">
              <img
                class="h-4 w-4"
                src="https://via.placeholder.com/150x50/000000"
                alt=""
              />
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
          <div class="text-center flex justify-center items-center text-xs poppins-font">
            <span class="flex-initial poppins-font">Built</span>
            <img
              class="h-4 w-4 mx-1"
              src="https://via.placeholder.com/150x50"
              alt="" />
            <span href="#" class="flex-initial poppins-font">
               on peexoo
            </span>
          </div>
        </div>
      </div>
      <div class="w-2/3 p-4">
        <div class="block">
          <button class="tab-button poppins-font active">Portfolio</button>
          <button class="tab-button poppins-font">Availability</button>
          <button class="tab-button poppins-font">Pricing Package</button>
        </div>
        <div class="flex text-sm">
          <div class="px-3 py-2 poppins-font flex-grow text-right">
            Sort by Image Category
          </div>
          <div
            class="px-3 py-2 poppins-font flex-initial bg-brand rounded lighter"
          >
            xx
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {}
}
</script>

<style lang="postcss" scoped>
/* @import '../assets/shared.css' */
.tab-button {
  @apply py-2 px-5 rounded-full mr-2 text-sm;
}
.tab-button:hover,
.tab-button.active {
  background: #fef3e0;
  @apply font-bold;
}
.breadcrumbs li {
  position: relative;
  @apply flex-initial pr-3 mr-2;
}
.breadcrumbs li:first-of-type {
  @apply text-gray-400;
}
.breadcrumbs.bulleted li:last-of-type::before {
  background: transparent;
}
.breadcrumbs li.fix {
  @apply mr-3;
}
.breadcrumbs.bulleted li::before {
  content: "";
  position: absolute;
  width: 5px;
  height: 5px;
  right: 0;
  top: 6px;
  background: black;
  border-radius: 500px;
}
.icon-button {
  background: #f7f7f7;
  @apply p-3 rounded-full mx-1;
}
</style>
