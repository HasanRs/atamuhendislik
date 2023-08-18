<script>
	export default {
		name: 'Footer',
	}
</script>
<template>
  <footer class="bg-white w-full border-t">
    <div class="px-4 py-12 mx-auto overflow-hidden max-w-7xl sm:px-6 lg:px-8">
      <nav class="flex flex-wrap justify-center -mx-5 -my-2" aria-label="Footer">
        <div class="px-5 py-2">
          <nuxt-link to="/" class="text-sm text-gray-500 hover:text-blue-600"> Anasayfa </nuxt-link>
        </div>

        <div class="px-5 py-2">
					<nuxt-link to="/projects" class="text-sm text-gray-500 hover:text-blue-600"> Projeler </nuxt-link>
        </div>

        <div class="px-5 py-2">
					<nuxt-link to="/blog" class="text-sm text-gray-500 hover:text-blue-600"> Blog </nuxt-link>
        </div>

        <div class="px-5 py-2">
					<nuxt-link to="/hakkimizda" class="text-sm text-gray-500 hover:text-blue-600"> Hakkımızda </nuxt-link>
        </div>

        <div class="px-5 py-2">
					<nuxt-link to="/iletisim" class="text-sm text-gray-500 hover:text-blue-600"> İletişim </nuxt-link>
        </div>
      </nav>
      <p class="mt-8 text-center">
        <span class="mx-auto mt-2 text-sm text-gray-500">
          Copyright © 2020 - 2021 Ata Mühendislik
          <a href="https://leodijital.com" class="mx-2 text-blue-500 hover:text-gray-500" rel="noopener noreferrer">
            Coded by Leo Dijital
          </a>
        </span>
      </p>
    </div>
  </footer>
</template>
