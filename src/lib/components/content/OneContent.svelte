<script>
  import Carosl from "./Carosl.svelte";

</script>
<section class="bg-gray-100">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-10 lg:py-20">
      <div class="md:flex md:justify-between md:items-center">
        <div class="md:w-1/2 lg:pr-10">
          <h1 class="text-3xl sm:text-4xl md:text-5xl font-bold text-gray-800 mb-4 sm:mb-6">Welcome to our consultancy firm</h1>
          <p class="text-base sm:text-lg md:text-xl text-gray-700 mb-6 sm:mb-8">We specialize in providing comprehensive solutions for businesses looking to enhance their production capabilities and product offerings in the personal hygiene industry.</p>
          <a href="#" class="inline-block bg-indigo-500 hover:bg-indigo-600 text-white py-3 px-6 rounded-md text-base sm:text-lg font-semibold">Get in touch</a>
        </div>
        <div class="md:w-1/2 lg:mt-0 mt-8">
          <Carosl/>
        </div>
      </div>
    </div>
  </section>
  