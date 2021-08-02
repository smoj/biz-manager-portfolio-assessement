<template>
  <div>
    <!-- Overlay Pictue Carousel -->
    <transition
        enter-active-class="animate__animated animate__fadeIn animate__faster"
        leave-active-class="animate__animated animate__fadeOut animate__faster"
      >
      <div v-if="showPictureGallery" class="z-50 fixed top-0 right-0 bottom-0 flex flex-col left-0 overlay-bg text-white">
        <div class="w-32 mx-auto my-8 text-center">
          <button @click="showPictureGallery = !showPictureGallery" class="px-4 py-2 text-white text-xs rounded-full font-bold poppins-font bg-white text-black close-btn">
            close
          </button>
        </div>
        <img
          class="w-2/5 mx-auto block rounded-md"
          src="@/assets/img/gallery-big-image.jpg"
          alt=""
        />
        <div class="mx-auto rounded-b-md w-2/5">
          <div class="text-black flex items-center poppins-font">
              <div class="flex-initial flex items-center p-3 bg-white rounded-b-md">
                <div class="p-2 flex-initial gallery-meta-icon-bg rounded-full mx-1 mr-2">
                  <img class="h-3 w-3" src="@/assets/img/heart-outline.png" alt="" />
                </div>
                <div class="p-2 flex-initial rounded-full mx-1 gallery-meta-icon-bg mr-2">
                  <img class="h-3 w-3" src="@/assets/img/heart-crossed-outline.png" alt="" />
                </div>
                <span class="mx-4 flex items-center">
                  <img class="h-3 w-3 mr-1" src="@/assets/img/heart-outline.png" alt="" />
                  <span class="text-sm">
                    5,349
                  </span>
                </span>
                <span class="mx-4 flex items-center">
                  <img class="h-3 w-3 mr-1" src="@/assets/img/heart-crossed-outline.png" alt="" />
                  <span class="text-sm">
                    23
                  </span>
                </span>
                <span class="mx-4 flex items-center">
                  <img class="h-5 w-5 mr-1" src="@/assets/img/eye-outline.png" alt="" />
                  <span class="text-sm">
                    24,023
                  </span>
                </span>
              </div>
          </div>
        </div>
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
        <div class="block sticky submenu z-40 bg-off-white py-4 flex items-center">
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
            <figure @click="showPictureGallery = true">
              <img class="w-7 h-7 z-10 mr-2 mt-2 mason-icon" src="@/assets/img/orange-heart.png" alt="">
              <img class="mason-image" src="https://assets.codepen.io/12005/windmill.jpg" alt="A windmill" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/suspension-bridge.jpg" alt="The Clifton Suspension Bridge" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="w-7 h-7 z-10 mr-2 mt-2 mason-icon" src="@/assets/img/orange-heart.png" alt="">
              <img class="mason-image" src="https://assets.codepen.io/12005/sunset.jpg" alt="Sunset and boats" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/snowy.jpg" alt="a river in the snow" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/bristol-balloons1.jpg" alt="a single checked balloon" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/dog-balloon.jpg" alt="a hot air balloon shaped like a dog" />
              <figcaption>
                <div class="flex-initial flex items-center p-3 bg-white rounded-b-md">
                  <div class="flex-grow w-1/4"></div>
                  <span class="mx-4 flex items-center">
                    <img class="h-3 w-3 mr-1" src="@/assets/img/heart-outline.png" alt="" />
                    <span class="text-sm">
                      5,349
                    </span>
                  </span>
                  <span class="mx-4 flex items-center">
                    <img class="h-3 w-3 mr-1" src="@/assets/img/heart-crossed-outline.png" alt="" />
                    <span class="text-sm">
                      23
                    </span>
                  </span>
                  <span class="mx-4 flex items-center">
                    <img class="h-5 w-5 mr-1" src="@/assets/img/eye-outline.png" alt="" />
                    <span class="text-sm">
                      24,023
                    </span>
                  </span>
                </div>
              </figcaption>
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/abq-balloons.jpg" alt="View from a hot air balloon of other balloons" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/disney-balloon.jpg" alt="a balloon fairground ride" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/bristol-harbor.jpg" alt="sunrise over a harbor" />
            </figure>
            <figure @click="showPictureGallery = true">
              <img class="mason-image" src="https://assets.codepen.io/12005/bristol-balloons2.jpg" alt="three hot air balloons in a blue sky" />
            </figure>
            <figure @click="showPictureGallery = true">
            <img src="https://assets.codepen.io/12005/toronto.jpg" alt="the Toronto light up sign at night" />
            </figure>
          </div>
        </div>

        <!-- Availability Content -->
        <div v-show="tabs.availability" class="block">
          <div :class="{'mx-24': !sidebarHidden}" class="flex items-center my-10">
            <div class="mr-8">
              <button class="p-2 icon-in-table rounded-full mx-1 flex-initial">
                <img class="h-6 w-6" src="@/assets/img/icon-arrow-left.png" alt="" />
              </button>
            </div>
            <div class="w-96">
              <div class="block py-3 text-center poppins-font">
                April 2020
              </div>
              <table class="table-fixed">
                <tbody>
                  <tr>
                    <th class="w-1/7 week-header day-cell">Sun</th>
                    <th class="w-1/7 week-header day-cell">Mon</th>
                    <th class="w-1/7 week-header day-cell">Tue</th>
                    <th class="w-1/7 week-header day-cell">Wed</th>
                    <th class="w-1/7 week-header day-cell">Thurs</th>
                    <th class="w-1/7 week-header day-cell">Fri</th>
                    <th class="w-1/7 week-header day-cell">Sat</th>
                  </tr>
                  <tr>
                    <th class="w-1/7 day-cell"></th>
                    <th class="w-1/7 day-cell"></th>
                    <th class="w-1/7 day-cell"></th>
                    <th class="w-1/7 day-cell">1</th>
                    <th class="w-1/7 day-cell">2</th>
                    <th class="w-1/7 day-cell">3</th>
                    <th class="w-1/7 day-cell">4</th>
                  </tr>
                  <tr>
                    <th class="w-1/7 day-cell">5</th>
                    <th class="w-1/7 day-cell">6</th>
                    <th class="w-1/7 day-cell">7</th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">8</div></th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">9</div></th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">10</div></th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">11</div></th>
                  </tr>
                  <tr>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">12</div></th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">13</div></th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">14</div></th>
                    <th class="w-1/7 day-cell"><div class="day-cell-circle">15</div></th>
                    <th class="w-1/7 day-cell">16</th>
                    <th class="w-1/7 day-cell">17</th>
                    <th class="w-1/7 day-cell">18</th>
                  </tr>
                  <tr>
                    <th class="w-1/7 day-cell">19</th>
                    <th class="w-1/7 day-cell">20</th>
                    <th class="w-1/7 day-cell">21</th>
                    <th class="w-1/7 day-cell">22</th>
                    <th class="w-1/7 day-cell">23</th>
                    <th class="w-1/7 day-cell">24</th>
                    <th class="w-1/7 day-cell">25</th>
                  </tr>
                </tbody>
              </table>
              <ul class="legend text-sm my-10">
                <li class="poppins-font">
                  <span class="inline-block mr-2 mb-1 text-brand">Booked</span>
                  <span class="inline-block mr-2 mb-1 text-lightest-gray">Orange shaded dates are booked days</span>
                </li>
                <li class="poppins-font">
                  <span class="inline-block mr-2 mb-1">Available</span>
                  <span class="inline-block mr-2 mb-1 text-lightest-gray">Unshaded dates are free days</span>
                </li>
              </ul>
            </div>
            <div class="ml-8">
              <button class="p-2 icon-in-table rounded-full mx-1 flex-initial">
                <img class="h-6 w-6" src="@/assets/img/icon-arrow-right.png" alt="" />
              </button>
            </div>
          </div>
        </div>

        <!-- Pricing Content -->
        <div v-show="tabs.pricing" class="block">
          <table class="table-fixed w-full">
            <thead class="bg-brand lighter rounded">
              <tr>
                <th class="w-1/5 cell-style text-left font-normal">Title</th>
                <th class="w-1/5 cell-style text-left font-normal">Category</th>
                <th class="w-1/5 cell-style text-center font-normal">Items</th>
                <th class="w-1/5 cell-style text-center font-normal">Date Created</th>
                <th class="w-1/5 cell-style text-right font-normal">Amount</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="w-1/5 cell-style text-left">Wedding Classic</td>
                <td class="w-1/5 cell-style text-left">Wedding</td>
                <td class="w-1/5 cell-style text-center">15</td>
                <td class="w-1/5 cell-style text-center">5th Sept 2020</td>
                <td class="w-1/5 cell-style text-right">N350,000</td>
              </tr>
              <tr @click="selectTab('package')">
                <td class="w-1/5 cell-style text-left">Beauty Campaign</td>
                <td class="w-1/5 cell-style text-left">Beauty</td>
                <td class="w-1/5 cell-style text-center">2</td>
                <td class="w-1/5 cell-style text-center">5th Sept 2020</td>
                <td class="w-1/5 cell-style text-right">N45,000</td>
              </tr>
              <tr>
                <td class="w-1/5 cell-style text-left">Prewedding Gold</td>
                <td class="w-1/5 cell-style text-left">Wedding</td>
                <td class="w-1/5 cell-style text-center">2</td>
                <td class="w-1/5 cell-style text-center">5th Sept 2020</td>
                <td class="w-1/5 cell-style text-right">N45,000</td>
              </tr>
              <tr>
                <td class="w-1/5 cell-style text-left">Culinary Photography</td>
                <td class="w-1/5 cell-style text-left">Food</td>
                <td class="w-1/5 cell-style text-center">18</td>
                <td class="w-1/5 cell-style text-center">5th Sept 2020</td>
                <td class="w-1/5 cell-style text-right">N75,000</td>
              </tr>
            </tbody>
          </table>
        </div>

        <!-- Package Summary -->
        <div v-show="tabs.package" class="block">
          <div class="flex items-center px-3 py-3">
            <button @click="selectTab('pricing')" class="text-brand text-sm mr-3 flex-initial">go back</button>
            <h5 class="text-sm flex-1 text-center font-semibold">Package Summary</h5>
          </div>
          <table class="table-fixed w-full">
            <thead class="bg-brand lighter rounded">
              <tr>
                <th class="w-2/5 cell-style text-left font-normal">Package Item</th>
                <th class="w-1/5 cell-style text-center font-normal">Quantity</th>
                <th class="w-1/5 cell-style text-left font-normal">Price</th>
                <th class="w-1/5 cell-style text-left font-normal">Amount</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td class="w-2/5 cell-style bg-white text-left">150 edited images</td>
                <td class="w-1/5 cell-style bg-white text-center">1</td>
                <td class="w-1/5 cell-style bg-white text-left">0</td>
                <td class="w-1/5 cell-style bg-white text-left">0</td>
              </tr>
              <tr>
                <td class="w-2/5 cell-style bg-white text-left">Pack of balloon</td>
                <td class="w-1/5 cell-style bg-white text-center">1</td>
                <td class="w-1/5 cell-style bg-white text-left">15000</td>
                <td class="w-1/5 cell-style bg-white text-left">15000</td>
              </tr>
            </tbody>
          </table>
          <div class="border-1 border-black opacity-5"></div>
          <table class="table-fixed w-full">
            <tbody>
              <tr>
                <td class="w-2/5 cell-style bg-white text-left">
                  <flex class="items-center">
                    <button class="p-2 icon-in-table rounded-full mr-2 flex-initial">
                      <img class="h-2 w-2" src="@/assets/img/logo-twitter.png" alt="" />
                    </button>
                    <span class="flex-1">Confetti and Flowers</span>
                  </flex>
                </td>
                <td class="w-1/5 cell-style bg-white text-center">2</td>
                <td class="w-1/5 cell-style bg-white text-left">3000</td>
                <td class="w-1/5 cell-style bg-white text-left">6000</td>
              </tr>
              <tr>
                <td class="w-2/4 py-4 px-3 poppins-font bg-white text-left text-xs">Service Charge</td>
                <td class="bg-white"></td>
                <td class="w-1/4 py-4 px-3 poppins-font bg-white text-left text-xs">10000</td>
                <td class="w-1/4 py-4 px-3 poppins-font bg-white text-left text-xs">10000</td>
              </tr>
              <tr>
                <td class="w-3/4 py-2 px-3 poppins-font bg-white text-left text-brand text-sm">Total</td>
                <td class="bg-white"></td>
                <td class="bg-white"></td>
                <td class="w-1/4 py-2 font-semibold px-3 poppins-font bg-white text-left text-sm">51,000</td>
              </tr>
            </tbody>
          </table>
          <div class="flex bg-white py-4 px-3">
            <button class="border border-1 px-3 py-2 poppins-font text-sm flex items-center">
              <span class="text-light-gray">Select Addons</span>
              <svg
                class="fill-current h-4 w-4 ml-2"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                    <path
                      d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                    />
                  </svg>
            </button>
            <div class="flex-grow"></div>
            <a
              href="#"
              class="
                px-4
                py-2
                rounded-full
                mx-1
                bg-brand
                poppins-font
                text-white text-sm
                flex-initial
              "
              >Select Package
            </a>
          </div>
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
      showPictureGallery: false,
      tabs: {
        portfolio: true,
        availability: false,
        pricing: false,
        package: false
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
  cursor: pointer;
}

figure .mason-icon {
  justify-self:end;
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
  /* padding: .2em .5em; */
  border: 1px solid transparent;
  justify-self:stretch;
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
.gallery-meta-icon-bg {
  background: #F5F5F5;
}
</style>
