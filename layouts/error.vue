<template>
  <main>
    <section>
      <template v-if="error.statusCode === 404">
        <div class="flex items-center justify-center h-screen bg-white">
          <div class="px-4 py-16 mx-auto text-center lg:px-8 lg:py-48 max-w-7xl sm:px-6 sm:py-24">
            <div class="justify-center w-full text-center lg:p-10 max-auto">
              <div class="justify-center w-full mx-auto">
                <p class="text-5xl tracking-tight lg:text-9xl">404</p>
                <p class="max-w-xl mx-auto mt-4 text-lg tracking-tight text-gray-400">
                  Aradığınız sayfa bulunamadı
                </p>
              </div>
              <div class="flex justify-center gap-3 mt-10">
                <nuxt-link
                  class="items-center justify-center w-full px-6 py-2.5 text-center text-white duration-200 bg-black border-2 border-black rounded-full nline-flex hover:bg-transparent hover:border-black hover:text-black focus:outline-none lg:w-auto focus-visible:outline-black text-sm focus-visible:ring-black"
                  to="/"
                >
                  Anasayfaya Geri Dön
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </template>
      <template v-else>
        <div class="flex items-center justify-center h-screen bg-white">
          <div class="px-4 py-16 mx-auto text-center lg:px-8 lg:py-48 max-w-7xl sm:px-6 sm:py-24">
            <div class="justify-center w-full text-center lg:p-10 max-auto">
              <div class="justify-center w-full mx-auto">
                <p class="text-5xl tracking-tight lg:text-9xl">Bir Hata oluştu</p>
              </div>
              <div class="flex justify-center gap-3 mt-10">
                <nuxt-link
                  class="items-center justify-center w-full px-6 py-2.5 text-center text-white duration-200 bg-black border-2 border-black rounded-full nline-flex hover:bg-transparent hover:border-black hover:text-black focus:outline-none lg:w-auto focus-visible:outline-black text-sm focus-visible:ring-black"
                  to="/"
                >
                  Anasayfaya Geri Dön
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </template>
    </section>
  </main>
</template>

<script>
export default {
  name: 'error',
  props: ['error'],
}
</script>
