<script>
  import { onMount } from 'svelte';

  let images = [
    { src: '/images/Hero.jpg', alt: 'Image 1' },
    { src: '/images/final.jpg', alt: 'Image 2' },
    { src: '/images/Computer.jpg', alt: 'Image 3' }
  ];

  let currentIndex = 0;
  let isClient = false;

  // Set isClient to true after component mounts
  onMount(() => {
    isClient = true;
    // Start autoplay
    setInterval(() => {
      nextSlide();
    }, 5000);
  });

  function nextSlide() {
    currentIndex = (currentIndex + 1) % images.length; 
  }

  function prevSlide() {
    currentIndex = (currentIndex - 1 + images.length) % images.length; 
  }
</script>

<section class="relative h-[80vh] overflow-hidden">
  {#if isClient}
    <div class="slider h-full w-full relative">
      {#each images as image, index}
        <div class="slide h-full w-full flex items-center justify-center bg-cover bg-center {index === currentIndex ? 'active' : ''}" style="background-image: url('{image.src}');">
          <div class="bg-black bg-opacity-30 w-full h-full flex items-center justify-center">
            <div class="text-white text-center p-4">
              <h1 class="text-5xl font-extrabold mb-4 animate-fade-in">Your Partner in Success</h1>
              <p class="text-xl mb-8 animate-fade-in">Get Your CSE Project Done Right!</p>
              <a href="#contact" class="bg-indigo-600 px-8 py-3 rounded-lg shadow-md text-lg font-bold animate-pulse hover:bg-indigo-700 transition">Contact Us</a>
            </div>
          </div>
        </div>
      {/each}

      <button class="prev" on:click={prevSlide}>&#10094;</button>
      <button class="next" on:click={nextSlide}>&#10095;</button>
    </div>
  {/if}
</section>

<style>
  section {
    height: 80vh;
    position: relative;
  }

  .slider {
    position: relative;
    height: 100%;
    overflow: hidden;
  }

  .slide {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
  }

  .slide.active {
    opacity: 1;
  }

  .prev,
  .next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    z-index: 10;
  }

  .prev {
    left: 10px;
  }

  .next {
    right: 10px;
  }

  .animate-fade-in {
    animation: fade-in 0.5s ease-in-out forwards;
  }

  @keyframes fade-in {
    from {
      opacity: 0;
      transform: translateY(-20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @media (max-width: 640px) {
    h1 {
      font-size: 3xl; 
    }
    p {
      font-size: lg; 
    }
    .bg-indigo-600 {
      padding: 0.5rem 1rem;
    }
  }
</style>
