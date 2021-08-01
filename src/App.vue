<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <div class="flex z-50 sticky top-0 items-center mx-0 mb-3 pt-3 pb-2 px-6 header-box-shadhow bg-white">
      <div>
        <img class="w-32" src="@/assets/img/logo.png" alt="">
      </div>
      <div class="spacer flex-grow"></div>
      <ul class="flex items-center">
        <li class="text-sm mx-2">
          <a class="nav-link poppins-font" href="#">Business Manager</a>
        </li>
        <li class="text-sm mx-2">
          <a class="nav-link poppins-font" href="#">Marketplace</a>
        </li>
        <li class="text-sm mx-2">
          <a class="nav-link poppins-font" href="#">XooCom</a>
        </li>
        <li class="text-sm mr-2 ml-32">
          <a class="text-brand poppins-font" href="#">Join Peexoo</a>
        </li>
      </ul>
    </div>
    <router-view/>
  </div>
</template>
