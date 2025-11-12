<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', e => {
      e.preventDefault()
      const targetId = anchor.getAttribute('href').substring(1)
      const target = document.getElementById(targetId)

      if (target) {
        target.scrollIntoView({ behavior: 'smooth' })
      }

      // Hilangkan # dari URL (hash)
      history.replaceState(null, null, ' ')
    })
  })
})

document.addEventListener("DOMContentLoaded", () => {
  const navbarsmall = document.getElementById("navbarsmall");
  const sentinel = document.getElementById("navbar-sentinel");

  const observer = new IntersectionObserver(
    (entries) => {
      const entry = entries[0];
      if (!entry.isIntersecting) {
        navbarsmall.classList.add("shadow-md");
      } else {
        navbarsmall.classList.remove("shadow-md");
      }
    },
    { rootMargin: "-1px 0px 0px 0px", threshold: 0 }
  );

  observer.observe(sentinel);
});

document.addEventListener("DOMContentLoaded", () => {
  const navbar = document.getElementById("navbar");
  const sentinel = document.getElementById("navbar-sentinel");

  const observer = new IntersectionObserver(
    (entries) => {
      const entry = entries[0];
      if (!entry.isIntersecting) {
        // artinya navbar udah nempel (sticky aktif)
        navbar.classList.add("shadow-md");
      } else {
        // masih belum nempel di atas
        navbar.classList.remove("shadow-md");
      }
    },
    { rootMargin: "-1px 0px 0px 0px", threshold: 0 }
  );

  observer.observe(sentinel);
});

import { ref } from 'vue'

// state reactive buat buka/tutup menu
const menuOpen = ref(false)

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}

import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import { Pagination, Navigation, Autoplay } from 'swiper/modules'
</script>

<template>
  <div class="font-primary box-border bg-whitey text-whitey">


    <!-- hero -->
    <div class="min-w-full min-h-screen bg-gradient-to-br from-secondary to-primary overflow-hidden flex relative">

      <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-top opacity-10 z-0"></div>

      <div
        class="max-w-screen-md lg:max-w-screen-lg w-full m-auto flex flex-col md:flex-row justify-center gap-10 opacity-100 z-10 px-10">
        <div class="my-auto flex flex-col gap-2">
          <div>
            <h1
              class="text-whitey font-extrabold text-6xl sm:text-8xl md:text-7xl lg:text-8xl leading-14 sm:leading-20 md:leading-14 lg:leading-18">
              BluePea</h1>
            <div class="flex">
              <h1
                class="text-whitey font-extrabold text-6xl sm:text-8xl md:text-7xl lg:text-8xl leading-14 sm:leading-20 md:leading-14 lg:leading-18">
                Bites</h1>
              <img src="/img/donutLogo.svg" alt="" class="h-auto w-24 lg:w-34">
            </div>
          </div>
          <p class="font-secondary text-whitey text-xl sm:text-xl md:text-lg">Naturally Sweet, Beautifully Healthy</p>
        </div>
        <div
          class="aspect-square w-74 lg:w-88 bg-[url('/img/donutMaskot.png')] bg-center bg-contain bg-no-repeat self-center">
        </div>
      </div>

    </div>

    <div id="navbar-sentinel"></div>
    <div id="navbar"
      class="h-18 sticky top-0 bg-whitey z-50 mt-2 transition-all duration-1000 ease-in-out hidden lg:flex">
      <div class="max-w-screen-lg m-auto w-full flex justify-between px-10 font-secondary">
        <img src="/img/donutMaskotPurple.png" alt="" onclick="window.scrollTo({ top: 0, behavior: 'smooth' })"
          class="my-auto h-auto w-12 cursor-pointer">
        <div class="flex justify-center items-center gap-12">
          <a href="#product"
            class="text-blackey text-lg hover:underline hover:underline-offset-6 decoration-wavy decoration-1">Products</a>
          <a href="#reason"
            class="text-blackey text-lg hover:underline hover:underline-offset-6 decoration-wavy decoration-1">BluePea</a>
          <a href="#team"
            class="text-blackey text-lg hover:underline hover:underline-offset-6 decoration-wavy decoration-1">Team</a>
          <button
            class="w-24 h-10 rounded-xl bg-primary text-lg shadow-hero-button hover:-translate-0.5 hover:shadow-hero-button-hover transition-all duration-50 cursor-pointer">
            <a href="https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A"
              target="_blank">Order</a>
          </button>

        </div>
      </div>
    </div>

    <!-- bar -->
    <div id="navbarsmall" class="fixed top-4 right-4 z-50 shadow-none lg:hidden">
      <div class="m-auto flex justify-between font-secondary">
        <img src="/img/donutMaskotPurple.png" alt="menu"
          class="w-12 cursor-pointer fixed top-5 right-5 z-50 hover:animate-spin active:animate-spin"
          @click="toggleMenu" />

        <!-- Overlay Menu -->
        <div
          class="fixed inset-0 flex flex-col justify-center items-center gap-20 transition-all duration-500 ease-in-out overflow-hidden"
          :class="menuOpen ? 'translate-y-0' : '-translate-y-full'">
          <!-- Lapisan blur di belakang -->
          <div class="absolute inset-0 bg-gradient-to-br from-primary/95 to-secondary/95"></div>

          <div class="relative z-10 flex flex-col items-center gap-24">
            <a href="#product"
              class="text-whitey font-semibold text-3xl hover:underline hover:underline-offset-6 active:underline active:underline-offset-6 decoration-whitey decoration-wavy decoration-1"
              @click="toggleMenu">Products</a>
            <a href="#reason"
              class="text-whitey font-semibold text-3xl hover:underline hover:underline-offset-6 active:underline active:underline-offset-6 decoration-whitey decoration-wavy decoration-1"
              @click="toggleMenu">BluePea</a>
            <a href="#team"
              class="text-whitey font-semibold text-3xl hover:underline hover:underline-offset-6 active:underline active:underline-offset-6 decoration-whitey decoration-wavy decoration-1"
              @click="toggleMenu">Team</a>

            <button
              class="w-24 h-10 rounded-xl bg-primary text-lg shadow-hero-button hover:-translate-0.5 hover:shadow-hero-button-hover transition-all duration-50 cursor-pointer hidden">
              <a href="https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A"
                target="_blank">Order</a>
            </button>
          </div>
        </div>
      </div>
    </div>


    <!--  -->
    <div class="text-blackey font-secondary mt-20 lg:mt-40 flex">
      <div class="flex flex-col m-auto max-w-screen-sm lg:max-w-screen-lg w-full px-10 lg:px-40">
        <h2 class="font-primary mb-6 lg:mb-8 text-3xl lg:text-4xl font-semibold">The Story Behind Our
          <span class="bg-gradient-to-br from-primary to-secondary bg-clip-text text-transparent">Blue</span>
        </h2>
        <div class="text-sm lg:text-base flex flex-col leading-9 lg:leading-6 gap-3 lg:gap-6 text-justify">
          <p>We’re a group of university students who share one simple passion
            <span class=" font-semibold">'we love desserts, but we care about living healthy too'.</span>
            We started experimenting with
            <span class="font-semibold">
              butterfly pea flowers,
            </span>those vibrant blue petals full of beauty and
            benefits.
          </p>
          <p>The result? A
            <span
              class="font-semibold text-3xl lg:text-4xl uppercase bg-secondary bg-clip-text text-transparent font-primary">Donut</span>
            that’s not just tasty, but meaningful and full of color.
          </p>

          <p>Each donut is <span class="font-semibold">baked</span> with <span class="font-semibold">natural
              ingredients</span> and colored with pure butterfly pea extract.
            Every bite is a blend of soft texture, gentle herbal aroma,
            and natural sweetness.</p>
        </div>
      </div>
    </div>

    <!-- products header -->
    <div class="min-h-screen flex flex-col">
      <h2 id="product"
        class="text-primary mx-auto text-4xl lg:text-6xl mt-20 scroll-mt-20 lg:scroll-mt-30 font-semibold lg:mt-40">Our
        Products
      </h2>

      <!-- container products -->
      <div class="max-w-screen-lg m-auto hidden lg:flex">

        <div
          class="mt-12 mx-10 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container">
          <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-bottom opacity-10 z-0"></div>

          <p class=" text-center font-secondary mt-10 text-5xl">All Variants only 7K</p>
          <div class="grid grid-cols-3 grid-rows-4 px-4 py-20 gap-y-30 gap-x-4">

            <div class="col-span-2 bg-whitey rounded-2xl h-30 ml-40 flex z-10 shadow-product-desc">
              <div
                class="text-secondary font-secondary m-auto pr-4 pl-46 flex flex-col justify-center items-center gap-2">
                <div class="text-2xl text-center leading-[1.75rem]">
                  Blue beauty with <span class="font-semibold">almond</span> and <span class="font-semibold">chia</span>
                  seed topping
                </div>
              </div>
            </div>
            <p class="text-5xl self-center">Signature <br>Butterfly</p>

            <p class="text-5xl self-center text-right">Matcha <br>Butterfly</p>
            <div class="col-span-2 bg-whitey rounded-2xl h-30 mr-40 flex z-10 shadow-product-desc">
              <div
                class="text-primary font-secondary m-auto pl-4 pr-46 flex flex-col justify-center items-center gap-2">
                <div class="text-2xl text-center leading-[1.75rem]">
                  A classic matcha with grated <span class="font-semibold">coconut</span> and <span
                    class="font-semibold">chia</span>
                </div>
              </div>
            </div>

            <div class=" col-span-2 bg-whitey rounded-2xl h-30 ml-40 flex z-10 shadow-product-desc">
              <div
                class="text-primary font-secondary m-auto pr-4 pl-44 flex flex-col justify-center items-center gap-1.5">
                <div class="text-2xl text-center leading-[1.75rem]">
                  A fresh mix of <span class="font-semibold">lemongrass</span> and <span
                    class="font-semibold">pistachio</span>
                </div>
              </div>
            </div>
            <p class="text-5xl self-center">Lemon <br>Butterfly</p>

            <p class="text-5xl self-center text-right">Chocolate <br>Butterfly</p>
            <div class="col-span-2 bg-whitey rounded-2xl h-30 mr-40 flex z-10 shadow-product-desc">
              <div
                class="text-secondary font-secondary m-auto pl-6 pr-47 flex flex-col justify-center items-center gap-2">
                <div class="text-2xl text-center leading-[1.75rem]">
                  Deep <span class="font-semibold">chocolate</span> flavor meets <span class="font-semibold">butterfly
                    pea</span>
                </div>
              </div>
            </div>

            <!-- gambar donut -->
            <img src="/img/donut3.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:rotate-6 hover:scale-105 hover:rotate-6 transition-all ease-in-out duration-750 top-30 left-10">
            <img src="/img/donut2.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:-rotate-6 hover:scale-105 hover:-rotate-6 transition-all ease-in-out duration-750 top-90 right-10">
            <img src="/img/donut1.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:rotate-6 hover:scale-105 hover:rotate-6 transition-all ease-in-out duration-750 bottom-64 left-10">
            <img src="/img/donut4.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:-rotate-6 hover:scale-105 hover:-rotate-6 transition-all ease-in-out duration-750 bottom-4 right-10">

            <p class="absolute font-secondary bottom-10 left-10">*Image just an illustration</p>
            <p class="absolute font-secondary bottom-5 left-10">*Available by pre-order only</p>
          </div>
        </div>

      </div>

      <!-- slider -->
      <section class="flex lg:hidden">
        <Swiper :modules="[Pagination, Navigation, Autoplay]" :slides-per-view="1" :space-between="50" :loop="true"
          :autoplay="{ delay: 3500, disableOnInteraction: false }" pagination class="mySwiper w-full">

          <!-- Slide 1 -->
          <SwiperSlide class="pb-10">
            <div
              class="mt-12 mx-10 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container group">
              <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-bottom opacity-10 z-0">
              </div>

              <div class="px-6 py-8 flex flex-col gap-4">
                <p class="text-4xl text-center">Signature <br>Butterfly</p>

                <img src="/img/donut3.png" alt=""
                  class="aspect-auto w-80 z-40 cursor-default group-active:scale-105 group-active:rotate-6 group-hover:scale-105 group-hover:rotate-6 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

                <p class="font-secondary text-center text-base">Topping: Telang glaze</p>

                <p class="font-secondary text-center text-4xl font-bold mb-8">Only 7K</p>
              </div>

              <p class="absolute font-secondary text-xs bottom-6 left-6">*Image just an illustration</p>
              <p class="absolute font-secondary text-xs bottom-2 left-6">*Available by pre-order only</p>
            </div>
          </SwiperSlide>

          <!-- Slide 2 -->
          <SwiperSlide class="pb-10">
            <div
              class="mt-12 mx-10 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container group">
              <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-bottom opacity-10 z-0">
              </div>

              <div class="px-6 py-8 flex flex-col gap-4">
                <p class="text-4xl text-center">Matcha <br>Butterfly</p>

                <img src="/img/donut2.png" alt=""
                  class="aspect-auto w-80 z-40 cursor-default group-active:scale-105 group-active:-rotate-6 group-hover:scale-105 group-hover:-rotate-6 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

                <p class="font-secondary text-center text-base">Topping: Matcha glaze, Almond</p>

                <p class="font-secondary text-center text-4xl font-bold mb-8">Only 7K</p>
              </div>

              <p class="absolute font-secondary text-xs bottom-6 left-6">*Image just an illustration</p>
              <p class="absolute font-secondary text-xs bottom-2 left-6">*Available by pre-order only</p>
            </div>
          </SwiperSlide>

          <!-- Slide 3 -->
          <SwiperSlide class="pb-10">
            <div
              class="mt-12 mx-10 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container group">
              <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-bottom opacity-10 z-0">
              </div>

              <div class="px-6 py-8 flex flex-col gap-4">
                <p class="text-4xl text-center">Chocolate <br>Butterfly</p>

                <img src="/img/donut4.png" alt=""
                  class="aspect-auto w-80 z-40 cursor-default group-active:scale-105 group-active:rotate-6 group-hover:scale-105 group-hover:rotate-6 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

                <p class="font-secondary text-center text-base">Topping: Chocolate glaze, Regal</p>

                <p class="font-secondary text-center text-4xl font-bold mb-8">Only 7K</p>
              </div>

              <p class="absolute font-secondary text-xs bottom-6 left-6">*Image just an illustration</p>
              <p class="absolute font-secondary text-xs bottom-2 left-6">*Available by pre-order only</p>
            </div>
          </SwiperSlide>

          <!-- Slide 4 -->
          <SwiperSlide class="pb-10">
            <div
              class="mt-12 mx-10 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container group">
              <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-bottom opacity-10 z-0">
              </div>

              <div class="px-6 py-8 flex flex-col gap-4">
                <p class="text-4xl text-center">Lemon <br>Butterfly</p>

                <!-- gambar donut -->
                <img src="/img/donut1.png" alt=""
                  class="aspect-auto w-80 z-40 cursor-default group-active:scale-105 group-active:rotate-6 group-hover:scale-105 group-hover:rotate-6 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

                <p class="font-secondary text-center text-base">Topping: Pistachio</p>

                <p class="font-secondary text-center text-4xl font-bold mb-8">Only 7K</p>
              </div>

              <p class="absolute font-secondary text-xs bottom-6 left-6">*Image just an illustration</p>
              <p class="absolute font-secondary text-xs bottom-2 left-6">*Not available yet</p>
            </div>
          </SwiperSlide>
        </Swiper>
      </section>

      <button
        class="fixed w-32 h-12 rounded-xl lg:hidden ring ring-primary bg-whitey font-bold text-base bottom-8 right-8 animate-bounce font-secondary z-40 shadow-preorder-button leading-4">
        <a class="text-primary" href="https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A"
          target="_blank">Pre-order<br>just opened!</a>
      </button>

    </div>


    <!-- why choose us -->
    <div class=" bg-gradient-to-b from-whitey to-secondary mt-0 lg:mt-40 px-5 flex flex-col">
      <p id="reason"
        class="font-primary text-blackey text-center text-4xl lg:text-5xl font-semibold scroll-mt-20 lg:scroll-mt-30">
        Why Choose
        BluePea Bites</p>
      <p class="font-secondary text-blackey text-center text-sm lg:text-base mt-4">Because our donuts are made not just
        to eat, but
        to enjoy with heart.</p>

      <div
        class="self-center grid grid-cols-1 grid-rows-4 lg:grid-cols-2 lg:grid-rows-4 mx-10 mt-14 font-secondary text-blackey gap-8 max-w-screen-sm">
        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
          <div class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
          </div>
          <img src="/img/reasonHealthy.png" alt=""
            class="absolute aspect-auto w-20 -top-6 -right-8.5 rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="/img/reasonHealthy.png" alt=""
            class="absolute aspect-auto w-28 -top-6 -left-11 -rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Healthy <br>Indulgence</p>
          <p class=" text-justify text-xs lg:text-sm z-10">Low sugar, preservative free, and baked for a lighter treat
          </p>
        </div>

        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
          <div class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
          </div>
          <img src="/img/reasonBlue.png" alt=""
            class="absolute aspect-auto w-20 -top-6 -left-7 -rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="/img/reasonBlue.png" alt=""
            class="absolute aspect-auto w-24 -top-9 -right-9 -rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Blue Magic <br>Aesthetic</p>
          <p class=" text-justify text-xs lg:text-sm z-10">Naturally blue from butterfly pea extract, beautiful and
            beneficial</p>
        </div>

        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
          <div class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
          </div>
          <img src="/img/reasonPrice.png" alt=""
            class="absolute aspect-auto w-24 -top-9 -right-8 rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="/img/reasonPrice.png" alt=""
            class="absolute aspect-auto w-30 -top-11 -left-16 -rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Student-Friendly <br>Price</p>
          <p class=" text-justify text-xs lg:text-sm z-10">Premium quality that fits a student’s budget</p>
        </div>

        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default">
          <div class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
          </div>
          <img src="/img/reasonLocal.png" alt=""
            class="absolute aspect-auto w-18 -top-4 -left-6 -rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="/img/reasonLocal.png" alt=""
            class="absolute aspect-auto w-22 -top-6 -right-6 rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Local <br>Production</p>
          <p class=" text-justify text-xs lg:text-sm z-10">Crafted by Indonesian students, made from local ingredients
          </p>
        </div>
      </div>
    </div>


    <!-- bg biru bawah -->
    <div class="bg-secondary font-secondary flex flex-col items-center pt-20 lg:pt-0 gap-4">
      <div class=" flex flex-col text-center text-2xl lg:text-5xl gap-4">
        <p>If you can't wait to order,</p>
        <p>just <span class="font-primary text-4xl lg:text-6xl">BITES</span> this <span
            class="font-primary text-4xl lg:text-6xl">DONUTS</span>
        </p>
      </div>
      <button
        class="h-40 lg:h-60 w-full flex justify-center hover:bg-whitey active:bg-whitey transition-all ease-in-out duration-100 group relative cursor-pointer"
        onclick="window.open('https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A', '_blank')">

        <img src="/img/donutLogo.svg" alt=""
          class="w-28 lg:w-40 absolute h-full animate-bounce transition-opacity duration-100 opacity-100 group-active:opacity-0 group-hover:opacity-0">

        <img src="/img/logoPurple.svg" alt=""
          class="w-28 lg:w-40 absolute h-full animate-bounce transition-opacity duration-100 opacity-0 group-active:opacity-100 group-hover:opacity-100" />

        <p
          class="opacity-0 group-active:opacity-100 group-hover:opacity-100 duration-100 text-2xl lg:text-8xl font-primary text-primary m-auto">
          Hit to</p>
        <p
          class="opacity-0 group-active:opacity-100 group-hover:opacity-100 duration-100 text-2xl lg:text-8xl font-primary text-primary m-auto">
          Order</p>
      </button>
    </div>

    <!-- team -->
    <div class=" bg-gradient-to-b from-secondary to-primary pt-30 lg:pt-60 px-10 relative lg:flex lg:flex-col">

      <p id="team" class=" text-center text-3xl lg:text-4xl scroll-mt-20 lg:scroll-mt-30">The Sweet Souls Behind BluePea
        Bites</p>
      <p class=" text-center font-secondary text-sm lg:text-lg mt-2">Meet the team that makes BluePea Bites possible</p>

      <div
        class="lg:self-center grid grid-cols-2 grid-rows-3 grid-flow-row lg:grid-cols-6 lg:grid-rows-3 lg:grid-flow-col mt-10 gap-y-4 gap-x-2 font-secondary lg:max-w-screen-lg">

        <!--  -->
        <div
          class="flex flex-col lg:row-start-1 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="/img/gina.png" alt="" class="aspect-auto drop-shadow-profile w-30 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Gina</p>
          <p class="text-sm">Founder & General Coordinator</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-2 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="/img/sandra.png" alt="" class="aspect-auto drop-shadow-profile w-18 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Sandra</p>
          <p class="text-sm">Marketing & Social Media</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-1 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="/img/myBaddieGueh.png" alt="" class="aspect-auto drop-shadow-profile w-24 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Farah</p>
          <p class="text-sm">Finance & Administration</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-2 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="/img/rizka.png" alt="" class="aspect-auto drop-shadow-profile w-28 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Rizka</p>
          <p class="text-sm">Production Manager</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-1 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="/img/dini.png" alt="" class="aspect-auto drop-shadow-profile w-24 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Dini</p>
          <p class="text-sm">Supply Chain & Logistics</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-2 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="/img/cazie.png" alt="" class="aspect-auto drop-shadow-profile w-20 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Cazie</p>
          <p class="text-sm">Customer Service & Sales</p>
        </div>

      </div>
    </div>

    <div class="bg-primary pt-40 lg:pt-60 text-right px-10 pb-40 lg:pb-60 flex flex-col">
      <div class="lg:max-w-screen-lg lg:m-auto lg:w-full">


        <p class=" text-3xl lg:text-5xl font-semibold mb-2">Ready for Your First Bite?</p>
        <p class=" font-secondary mb-8 lg:mb-14 text-md lg:text-xl">We open pre-orders only on weekend</p>

        <div class="flex font-secondary text-md lg:text-xl">
          <button
            class="grow ring-3 rounded-xl cursor-pointer h-14 lg:h-20 hover:bg-whitey active:bg-whitey group transition-all ease-in-out duration-100"
            onclick="window.open('https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A', '_blank')">
            <span
              class="group-hover:bg-gradient-to-br group-active:bg-gradient-to-br group-hover:from-primary group-active:from-primary group-hover:to-secondary group-active:to-secondary group-hover:bg-clip-text group-active:bg-clip-text group-hover:text-transparent group-active:text-transparent transition-all ease-in-out duration-1000">Bites
              First, Think Later</span>
          </button>
        </div>

      </div>
    </div>

    <!--  -->
    <div class="w-full h-full bg-whitey font-secondary text-blackey py-6 px-5 lg:px-10">
      <div class="flex justify-between text-xs lg:text-sm">
        <div class="flex flex-col gap-4">
          <div>
            <p class="font-bold">Location</p>
            <a href="https://maps.app.goo.gl/5wY1twKtwNs1nKKo8" target="_blank" rel="noopener noreferrer"
              class="flex items-center gap-2 hover:underline active:underline decoration-wavy decoration-1 underline-offset-2">
              <span class="icon-[mdi--map-marker] scale-125"></span>
              <p>Jatinangor</p>
            </a>
          </div>

          <div>
            <p class="font-bold">Contact</p>
            <a href="mailto:bluepeabites@gmail.com" target="_blank"
              class="flex items-center gap-2 hover:underline active:underline decoration-wavy decoration-1 underline-offset-2">
              <span class="icon-[ic--baseline-email] scale-110 cursor-pointer"></span>
              <p>bluepeabites@gmail.com</p>
            </a>
            <a href="https://instagram.com/bluepea.bites" target="_blank" rel="noopener noreferrer"
              class="flex items-center gap-2 hover:underline active:underline decoration-wavy decoration-1 underline-offset-2">
              <span class="icon-[mdi--instagram] scale-110 cursor-pointer"></span>
              <p>@bluepea.bites</p>
            </a>
            <a href="https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A"
              target="_blank" rel="noopener noreferrer"
              class="flex items-center gap-2 hover:underline active:underline decoration-wavy decoration-1 underline-offset-2">
              <span class="icon-[ic--baseline-whatsapp] scale-110 cursor-pointer"></span>
              <p>0812-2040-6031</p>
            </a>
          </div>
        </div>

        <div class="flex flex-col text-right">
          <p>©2025 BluePea Bites</p>
          <p>Naturally Sweet, Beautifully Healthy</p>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped></style>
