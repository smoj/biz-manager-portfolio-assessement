<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <div class="flex mx-0 my-3 pb-3 px-6 header-box-shadhow bg-white">
      <div>
        <img src="https://via.placeholder.com/150x50" alt="">
      </div>
      <div class="spacer flex-grow"></div>
      <ul class="flex items-center">
        <li class="text-sm mx-2">
          <a class="text-black poppins-font" href="#">Business Manager</a>
        </li>
        <li class="text-sm mx-2">
          <a class="text-black poppins-font" href="#">Marketplace</a>
        </li>
        <li class="text-sm mx-2">
          <a class="text-black poppins-font" href="#">XooCom</a>
        </li>
        <li class="text-sm mr-2 ml-32">
          <a class="text-brand poppins-font" href="#">Join Peexoo</a>
        </li>
      </ul>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  background: #FFFDF7;
}

</style>
