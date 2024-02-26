<script>
export default {};
</script>

<template>
  <div class="relative">
    <div class="absolute w-full flex items-center justify-center top-8">
      <h1 class="lg:text-8xl text-gray-950 font-headline text-4xl">
        Hudson Ski Resort
      </h1>
    </div>
    <div
      class="material-symbols-outlined absolute bottom-4 text-slate-100 text-5xl animate-bounce w-full flex items-center justify-center"
    >
      <span class="self-center bg-black select-none rounded-full"
        >arrow_downward</span
      >
    </div>
    <video
      class="h-dvh lg:h-lvh lg:w-full lg:object-fill object-cover"
      src="../assets/videos/mountain.mp4"
      autoplay
      loop
    ></video>
  </div>
</template>
