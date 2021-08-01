<template>
  <div>
    <!-- Overlay Profile Picture -->
    <transition
        enter-active-class="animate__animated animate__fadeIn animate__faster"
        leave-active-class="animate__animated animate__fadeOut animate__faster"
      >
      <div v-if="showProfilePic" class="z-50 fixed top-0 right-0 bottom-0 flex flex-col left-0 overlay-bg text-white">
        <div class="w-32 mx-auto mt-8 mb-24">
          <button @click="showProfilePic = !showProfilePic" class="px-4 py-2 text-white text-xs rounded-full font-bold poppins-font bg-white text-black close-btn">
            close image
          </button>
        </div>
        <img
          class="w-72 h-72 mx-auto block"
          src="@/assets/img/tim_mcbaj_53652000_2255623191378916_4966133143083590398_n@2x.png"
          alt=""
        />
        <div class="v-spacer flex-1"></div>
        <div class="
                text-center
                flex
                justify-center
                brand-gray
                items-center
                text-xs
                poppins-font
                my-5
              "
            >
              <span class="flex-initial text-white poppins-font">Built for free</span>
              <img
                class="h-5 w-5 mx-1"
                src="@/assets/img/logo-heart-filled.png"
                alt=""
              />
              <span href="#" class="flex-initial text-white poppins-font"> on Peexoo </span>
            </div>
      </div>
    </transition>
    <!-- Banner Image -->
    <div class="rounded-md bg-gray-600 h-32 mx-3 banner-image">.</div>

    <!-- Profile Sidebar -->
    <div class="flex mx-10">
      <transition
        enter-active-class="animate__animated animate__fadeIn animate__faster"
        leave-active-class="animate__animated animate__fadeOut animate__faster"
      >
        <profile-sidebar @on-show-profile-pic="toggleProfilePic" @on-hidden="hideSidebar" v-if="!sidebarHidden" :class="{'fixed': !sidebarHidden}" class="top-24" />
      </transition>
      <div :class="{'ml-96' : !sidebarHidden}" class="flex-1 p-4">
        <!-- submenu -->
        <div class="block sticky submenu bg-off-white py-4 flex items-center">
          <a href="#" @click="sidebarHidden = false" :class="{'hidden' : !sidebarHidden}" class="text-left w-1/4">
            <img
              class="w-10 h-10 mr-2 inline-block"
              src="@/assets/img/tim_mcbaj_53652000_2255623191378916_4966133143083590398_n.png"
              alt=""
            />
            <span class="text-brand">Portfolio</span>
          </a>
          <div :class="{'w-2/4': sidebarHidden, 'w-3/4': !sidebarHidden, 'justify-center': sidebarHidden}" class="flex">
            <button class="tab-button poppins-font" :class="{'active': tabs.portfolio}" @click="selectTab('portfolio')">Portfolio</button>
            <button class="tab-button poppins-font" :class="{'active': tabs.availability}" @click="selectTab('availability')">Availability</button>
            <button class="tab-button poppins-font" :class="{'active': tabs.pricing}" @click="selectTab('pricing')">Pricing Package</button>
          </div>
        </div>

        <!-- Portfolio Content -->
        <div v-show="tabs.portfolio" class="block">
          <!-- Dropdown -->
          <div :class="{'hidden': sidebarHidden}" class="flex text-sm mb-3">
            <div class="px-3 py-2 poppins-font brand-gray flex-grow text-right">
              Sort by Image Category
            </div>
            <div
              class="poppins-font flex-initial bg-brand rounded lighter"
            >
              <div class="group inline-block relative">
                <button
                  class="
                    drowdown-bg
                    text-gray-700
                    py-2
                    px-4
                    rounded
                    inline-flex
                    items-center
                  "
                >
                  <span class="mr-2">All</span>
                  <svg
                    class="fill-current h-4 w-4"
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 20 20"
                  >
                    <path
                      d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                    />
                  </svg>
                </button>
                <ul class="absolute hidden w-48 right-0 text-gray-700 pt-1 group-hover:block">
                  <li class="">
                    <a
                      class="rounded-t bg-white py-2 px-4 block whitespace-no-wrap text-right"
                      href="#"
                      >Food
                    </a>
                    <a
                      class="rounded-t bg-white py-2 px-4 block whitespace-no-wrap text-right"
                      href="#"
                      >Wedding Images
                    </a>
                    <a
                      class="rounded-t bg-white py-2 px-4 block whitespace-no-wrap text-right"
                      href="#"
                      >Portraits
                    </a>
                    <a
                      class="rounded-t bg-white py-2 px-4 block whitespace-no-wrap text-right"
                      href="#"
                      >Model Shots
                    </a>
                  </li>
                </ul>
              </div>
            </div>
          </div>

          <!-- Masonry Content -->
          <div class="masonry-container">
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/windmill.jpg" alt="A windmill" />
              <figcaption><a href="#">1</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/suspension-bridge.jpg" alt="The Clifton Suspension Bridge" />
              <figcaption><a href="#">2</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/sunset.jpg" alt="Sunset and boats" />
              <figcaption><a href="#">3</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/snowy.jpg" alt="a river in the snow" />
              <figcaption><a href="#">4</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/bristol-balloons1.jpg" alt="a single checked balloon" />
              <figcaption><a href="#">5</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/dog-balloon.jpg" alt="a hot air balloon shaped like a dog" />
              <figcaption><a href="#">6</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/abq-balloons.jpg" alt="View from a hot air balloon of other balloons" />
              <figcaption><a href="#">7</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/disney-balloon.jpg" alt="a balloon fairground ride" />
              <figcaption><a href="#">8</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/bristol-harbor.jpg" alt="sunrise over a harbor" />
              <figcaption><a href="#">9</a></figcaption>
            </figure>
            <figure>
              <img class="mason-image" src="https://assets.codepen.io/12005/bristol-balloons2.jpg" alt="three hot air balloons in a blue sky" />
              <figcaption><a href="#">10</a></figcaption>
            </figure>
            <figure>
            <img src="https://assets.codepen.io/12005/toronto.jpg" alt="the Toronto light up sign at night" />
              <figcaption><a href="#">11</a></figcaption>
            </figure>
          </div>
        </div>

        <!-- Availability Content -->
        <div v-show="tabs.availability" class="block">
          Availability Content
        </div>

        <!-- Pricing Content -->
        <div v-show="tabs.pricing" class="block">
          Pricing Content
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import ProfileSidebar from '@/components/profileSidebar.vue'
import 'animate.css'
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    ProfileSidebar
  },
  data () {
    return {
      sidebarHidden: false,
      showProfilePic: false,
      tabs: {
        portfolio: true,
        availability: false,
        pricing: false
      }
    }
  },
  computed: {
    getTabs () {
      return Object.keys(this.tabs)
    }
  },
  methods: {
    hideSidebar () {
      console.log('sidebar hide activated')
      this.sidebarHidden = !this.sidebarHidden
    },
    toggleProfilePic () {
      this.showProfilePic = !this.showProfilePic
    },
    selectTab (tabName) {
      this.resetTabs()
      this.$set(this.tabs, tabName, true)
    },
    resetTabs () {
      this.getTabs.forEach((tab) => {
        this.$set(this.tabs, tab, false)
      })
    }
  }
}
</script>

<style lang="postcss" scoped>
figure {
  margin: 0;
  display: grid;
  grid-template-rows: 1fr auto;
  margin-bottom: 10px;
  break-inside: avoid;
}

figure > img {
  grid-row: 1 / -1;
  grid-column: 1;
  max-width: 100%;
  display: block;
}

figure a {
  color: black;
  text-decoration: none;
}

figcaption {
  grid-row: 2;
  grid-column: 1;
  background-color: rgba(255,255,255,.5);
  padding: .2em .5em;
  justify-self: start;
}

.masonry-container {
  column-count: 3;
  column-gap: 10px;
}
.mason-image {
  @apply rounded-md
}
.mason-image:hover {
  border: 1px solid #f09e28;
}
.close-btn {
  background-color: rgba(255,255,255,.09);
}
</style>
