<script>
export default {
  name: 'Header',
  data() {
    return {
      open: false,
    }
  },
}
</script>
<template>
  <div class="w-full mx-auto bg-white border-b 2xl:max-w-7xl">
    <div
      x-data="{ open: false }"
      class="relative flex flex-col w-full p-5 mx-auto bg-white md:items-center md:justify-between md:flex-row md:px-6 lg:px-8"
    >
      <div class="flex flex-row items-center justify-between lg:justify-start">
        <nuxt-link class="text-lg tracking-tight text-black uppercase focus:outline-none focus:ring lg:text-2xl" to="/">
          <img src="../../assets/images/atamuhlogo.png" alt="logo" class="w-28 h-14" />
        </nuxt-link>
        <button
          @click="open = !open"
          class="inline-flex items-center justify-center p-2 text-gray-400 hover:text-black focus:outline-none focus:text-black md:hidden"
        >
          <svg class="w-6 h-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
            <path
              :class="{ hidden: open, 'inline-flex': !open }"
              class="inline-flex"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
            <path
              :class="{ hidden: !open, 'inline-flex': open }"
              class="hidden"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            ></path>
          </svg>
        </button>
      </div>
      <nav
        :class="{ flex: open, hidden: !open }"
        class="flex-col items-center flex-grow hidden md:pb-0 md:flex md:justify-end md:flex-row"
      >
        <nuxt-link class="px-2 py-2 text-sm text-gray-500 lg:px-6 md:px-3 hover:text-blue-600 lg:ml-auto" to="/"> Anasayfa </nuxt-link>
        <nuxt-link class="px-2 py-2 text-sm text-gray-500 lg:px-6 md:px-3 hover:text-blue-600" to="/projects"> Projeler </nuxt-link>
        <nuxt-link class="px-2 py-2 text-sm text-gray-500 lg:px-6 md:px-3 hover:text-blue-600" to="/blog"> Blog </nuxt-link>
        <nuxt-link class="px-2 py-2 text-sm text-gray-500 lg:px-6 md:px-3 hover:text-blue-600" to="/hakkimizda"> Hakkımızda </nuxt-link>

        <div class="inline-flex items-center gap-2 list-none lg:ml-auto">
          <nuxt-link
            class="inline-flex items-center justify-center px-4 py-2 text-sm font-semibold text-white bg-black rounded-full group focus:outline-none focus-visible:outline-2 focus-visible:outline-offset-2 hover:bg-gray-700 active:bg-gray-800 active:text-white focus-visible:outline-black"
            to="/iletisim"
          >
            İletişim
          </nuxt-link>
        </div>
      </nav>
    </div>
  </div>
</template>
