<script>
    import { onMount } from 'svelte';
    
    const images = [
      'https://picsum.photos/id/45/500',
      'https://picsum.photos/id/33/500',
      'https://picsum.photos/id/32/500',
      'https://picsum.photos/id/35/500'
    ];
  
    let captions = [
    "Caption for Image 1",
    "Caption for Image 2",
    "Caption for Image 3",
    "Caption for Image 4",
    "Caption for Image 5"
  ];

  let activeIndex = 0;
  let interval;

  function next() {
    activeIndex = (activeIndex + 1) % images.length;
  }

  function prev() {
    activeIndex = (activeIndex - 1 + images.length) % images.length;
  }

  function startInterval() {
    interval = setInterval(next, 5000);
  }

  startInterval();
  </script>
  
  <div class="relative">
    <!-- Images -->
    {#each images as image, i}
    <img src={image} class={i === activeIndex ? "block mx-auto" : "hidden absolute inset-0"} alt="Carousel image">
    <figcaption class="absolute inset-0 flex items-center justify-center text-white text-lg font-bold opacity-0 transition duration-200 ease-out bg-black bg-opacity-50 hover:opacity-100">
      {captions[i]}
    </figcaption>
  {/each}

  
    <!-- Navigation buttons -->
    <button on:click={prev} class="absolute inset-y-0 left-0 flex items-center justify-center w-12 text-white bg-black bg-opacity-50 hover:bg-opacity-75 transition duration-200 ease-out rounded-l-md focus:outline-none {activeIndex === 0 && 'opacity-50 cursor-default'}">
      <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
      </svg>
    </button>
    <button on:click={next} class="absolute inset-y-0 right-0 flex items-center justify-center w-12 text-white bg-black bg-opacity-50 hover:bg-opacity-75 transition duration-200 ease-out rounded-r-md focus:outline-none {activeIndex === images.length - 1 && 'opacity-50 cursor-default'}">
      <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
      </svg>
    </button>
  </div>
  
  