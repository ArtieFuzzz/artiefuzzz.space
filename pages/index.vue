<script setup lang='ts'>
import '@/assets/main.css'
</script>

<template>
  <div class='prose prose-zinc lg:prose-xl w-screen h-screen'>
    <div class='flex flex-col justify-center items-center h-screen w-screen'>
      <img src='/profilepic.png' alt='Profile Picture' class='round-pfp' size='256' draggable='false'>
      <h1 class='main-title'>
        ArtieFuzzz
      </h1>
      <Icons class='flex justify-center place-items-start' />
      <h2 class='main-tagline'>
        Self - Taught Full Stack Developer
      </h2>
    </div>

    <div class=' mx-auto text-center items-center justify-center'>
      <footer
        class='text-center align-bottom lg:fixed inset-x-0 bottom-10 text-white'
        style='fontSize: 1rem'  
      >
        Copyright &copy; 2022 - Present |
        <a href='https://github.com/ArtieFuzzz' class='text-white umami--click--footer-profile'> ArtieFuzzz </a> | (
        <a href='https://www.pixiv.net/en/artworks/97122460' class='text-white umami--click--footer-bg-source'>
          Background Source
        </a>
        )
        <br />
        <a href='https://www.flaticon.com/free-icons/rose' title='rose icons' class='text-white umami--click--footer-attribute'>
          Rose icons created by Freepik - Flaticon
        </a>
      </footer>
    </div>
  </div>
</template>

<style>
  .main-title {
    @apply text-7xl font-bold m-0 text-white mb-[0.71rem];
  }

  .main-tagline {
    @apply text-pink-300 font-semibold m-0 mt-[20px];
    font-size: 1rem;
    line-height: 1.25rem;
  }

  .round-pfp {
    @apply rounded-full ring-4 p-1 dark:ring-gray-800 ring-pink-300 m-0 mb-[1rem];
  }
</style>
