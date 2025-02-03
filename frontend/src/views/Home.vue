<script setup>
import Emails from "../components/Emails.vue";
import TypeWriter from "@/components/TypeWriter.vue";
import Button from "@/components/Button.vue";
</script>

<template>
  <div class="relative font-[Poppins] min-h-screen w-full">
    <img
      src="@/assets/icons/background2.jpg"
      class="absolute top-0 left-0 w-full h-full object-cover"
    />

    <div
      class="relative w-full h-full flex flex-col md:flex-row items-center min-h-screen pt-[56px]"
    >
      <div class="w-full flex flex-col ml-8 p-4 md:w-1/2 z-10">
        <div><TypeWriter /></div>
        <p
          class="text-white font-bold text-3xl sm:text-4xl md:text-6xl lg:text-7xl w-[70%] leading-tight underline mt-6"
        >
          The Art Shop
        </p>
        <p
          class="text-white font-bold text-2xl sm:text-2xl md:text-4xl lg:text-5xl w-[80%] leading-tight mt-10"
        >
          Art to appreciate
        </p>
        <p class="text-white text-md md:text-xl lg:text-3xl w-[90%] mt-2">
          A showcase of beautiful and iconic art created throughout history.
        </p>
      </div>
      <div>
        <Button />
      </div>
      <div class="w-full md:w-1/2 z-10 flex md:justify-end md:mr-8 p-4">
        <Emails />
      </div>
    </div>
    <div
      class="pointer-events-none absolute bottom-0 left-0 w-full h-[92px] bg-gradient-to-b from-transparent to-[#000612]"
    ></div>
  </div>
</template>
