<script>
export default {
	name: 'HeroSection',
}
</script>
<template>
  <section>
    <div class="relative items-center w-full px-5 py-24 mx-auto md:px-12 lg:px-16 max-w-7xl">
      <div class="relative flex-col items-start m-auto align-middle">
        <div class="grid grid-cols-1 gap-6 lg:grid-cols-2 lg:gap-24">
          <div class="relative items-center gap-12 m-auto lg:inline-flex md:order-first">
            <div class="max-w-xl text-center lg:text-left">
              <div>
                <p class="text-2xl font-medium tracking-tight text-black sm:text-4xl">ATA MÜHENDİSLİK <br>ELEKTRİK PROJE</p>
                <p class="max-w-xl mt-4 text-base tracking-tight text-gray-600">
                  Kurumsal bir yaklaşımla müşteri taleplerini en üst seviyede değerlendiren, kaliteden ödün vermeden ARGE çalışmalarına büyük önem gösteren profesyonel ekibi ve proje kadrosuyla, elektrik projelerinizin her türlü ihtiyacına yönelik çözümler sunmaya hazırız.
                </p>
              </div>
              <div class="flex flex-col items-center justify-center gap-3 mt-10 lg:flex-row lg:justify-start">
                <nuxt-link
                  to="/projects"
                  class="items-center justify-center w-full px-6 py-2.5 text-center text-white duration-200 bg-black border-2 border-black rounded-full inline-flex hover:bg-transparent hover:border-black hover:text-black focus:outline-none lg:w-auto focus-visible:outline-black text-sm focus-visible:ring-black"
                >
                  Projelerimiz
                </nuxt-link>
                <nuxt-link
                  to="/iletisim"
                  class="inline-flex items-center justify-center text-sm font-semibold text-black duration-200 hover:text-blue-500 focus:outline-none focus-visible:outline-gray-600"
                >
                  İletişime Geç &nbsp; →
                </nuxt-link>
              </div>
            </div>
          </div>
          <div class="order-first block w-full mt-12 aspect-square lg:mt-0">
            <img
              class="object-cover object-center w-full mx-auto bg-gray-300 border lg:ml-auto"
              alt="hero"
              src="https://images.unsplash.com/photo-1691767971416-2df5d50bcdc3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1015&q=80"
            />
          </div>
        </div>
      </div>
      <div>
        <div class="pt-12 mx-auto lg:max-w-7xl">
          <dl class="grid grid-cols-1 gap-6 space-y-0 text-center lg:gap-24 lg:grid-cols-3 lg:text-left">
            <div>
              <div>
                <p class="mt-5 text-lg font-medium leading-6 text-black">Zaman Yönetimi</p>
              </div>
              <div class="mt-2 text-base text-gray-500">
                Zaman her şey demektir.
                Sizin adınıza işletmenizde denetimler gerçekleştirelim ve olası kazaların önüne birlikte geçelim.
              </div>
            </div>
            <div>
              <div>
                <p class="mt-5 text-lg font-medium leading-6 text-black">Proje Yönetimi</p>
              </div>
              <div class="mt-2 text-base text-gray-500">
                Firmamız proje ekibiyle elektrik proje konusundaki her türlü ihtiyacınıza çözüm üretmeye hazırdır. 
              </div>
            </div>
            <div>
              <div>
                <p class="mt-5 text-lg font-medium leading-6 text-black">Güvenlik</p>
              </div>
              <div class="mt-2 text-base text-gray-500">
                Siz ve çalışanlarınızın güvenliği önceliğimizdir.
              </div>
            </div>
          </dl>
        </div>
      </div>
    </div>
  </section>
</template>
