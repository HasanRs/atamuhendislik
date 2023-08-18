<script>
export default {
		name: 'BlogSection',
	}
</script>

<template>
  <section class="bg-gray-100">
		<div class="relative items-center w-full px-5 py-12 mx-auto md:px-12 lg:px-20 max-w-7xl">
			<h2 class="text-3xl font-extrabold leading-8 tracking-tight text-center text-black sm:text-4xl">
				Blog Yazılarımız
			</h2>
			<div class="relative flex items-center justify-center w-full max-w-2xl mx-auto mt-6">
				<p class="text-base text-center text-gray-500">
					Bilgi dolu içeriklerimizle donattığımız blogumuzda elektrik projelerinden ilham verici trendlere kadar geniş bir yelpazede konuları ele alıyoruz. 
					Size rehberlik etmek, fikir sunmak ve sizi bilgilendirmek için buradayız. 
				</p>
			</div>
		</div>
    <div class="relative items-center w-full px-5 py-12 mx-auto md:px-12 lg:px-20 max-w-7xl">
      <posts post-type="blog" :amount="3" />
    </div>
  </section>
</template>
