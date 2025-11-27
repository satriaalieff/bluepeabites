<script setup>
import { Icon } from "@iconify/vue";
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay, EffectCards, FreeMode } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/free-mode'
import 'swiper/css/effect-cards'

const modules = [Autoplay, FreeMode, EffectCards]

const reviews = [
  {
    name: 'Ameera',
    rating: 5,
    review: 'Donutnya yummy banget!',
    variants: 'Signature, Matcha'
  },
  {
    name: 'Furi',
    rating: 5,
    review: 'Manisnya pas banget',
    variants: 'Signature, Matcha'
  },
  {
    name: 'Keysa',
    rating: 5,
    review: 'So fluffy omg omg',
    variants: 'Matcha, Chocolate'
  },
  {
    name: 'Satria',
    rating: 5,
    review: 'JCO sama Dunkin kalah ini mah',
    variants: 'Signature, Matcha, Chocolate'
  },
  {
    name: 'Salsa',
    rating: 5,
    review: 'Jujur ini donut paling enak di nangor',
    variants: 'Matcha'
  },
  {
    name: 'Ersa',
    rating: 5,
    review: 'Sweet but not too much',
    variants: 'Signature, Matcha, Chocolate'
  },
  {
    name: 'Vicensa',
    rating: 5,
    review: 'Demi apapun matcha nya enak bangetttt',
    variants: 'Matcha'
  },
  {
    name: 'Rifky',
    rating: 5,
    review: 'Jujur enak, mau lagi pls',
    variants: 'Matcha'
  },
  {
    name: 'Selly',
    rating: 5,
    review: 'Enak banget donutnya best!',
    variants: 'Chocolate'
  },
  {
    name: 'Safira',
    rating: 5,
    review: 'Selain donutnya enak, penjualnya juga seru seru',
    variants: 'Matcha'
  },
  {
    name: 'Yudha',
    rating: 5,
    review: 'Donut favorit baru',
    variants: 'Signature, Matcha, Chocolate'
  },
  {
    name: 'Alwan',
    rating: 5,
    review: 'Donutnya lucu, rasanya nagih',
    variants: 'Matcha, Chocolate'
  },
  {
    name: 'Riva',
    rating: 5,
    review: 'KAPAN OPEN PO KEDUA? MAU!!',
    variants: 'Signature, Matcha, Chocolate'
  },
  {
    name: 'Luthvia',
    rating: 5,
    review: 'Packagingnya terlucu dari yang lain',
    variants: 'Signature'
  },
];
</script>

<template>
  <div class="font-primary box-border bg-whitey text-whitey scroll-smooth">

    <!-- hero -->
    <div class="min-w-full min-h-screen bg-gradient-to-br from-secondary to-primary overflow-hidden flex relative">

      <div class="absolute inset-0 bg-[url('@/assets/pattern/linePattern.png')] bg-cover bg-top opacity-10 z-0"></div>

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
              <img src="@/assets/img/donutLogo.svg" alt="" class="h-auto w-24 lg:w-34">
            </div>
          </div>
          <p class="font-secondary text-whitey text-xl sm:text-xl md:text-lg">Naturally Sweet, Beautifully Healthy</p>
        </div>
        <div
          class="aspect-square w-74 lg:w-88 bg-[url('@/assets/img/donutMaskot.png')] bg-center bg-contain bg-no-repeat self-center">
        </div>
      </div>
    </div>

    <div id="navbar" class="h-18 sticky top-0 bg-whitey z-50 hidden lg:flex shadow-sm">
      <div class="max-w-screen-lg m-auto w-full flex justify-between px-10 font-secondary">
        <img src="@/assets/img/donutMaskotPurple.png" alt="" onclick="window.scrollTo({ top: 0, behavior: 'smooth' })"
          class="my-auto h-auto w-12 cursor-pointer">
        <div class="flex justify-center items-center gap-12">
          <a href="#product"
            class="text-blackey text-lg active:underline active:underline-offset-6 hover:underline hover:underline-offset-6 decoration-wavy decoration-1">Products</a>
          <a href="#reason"
            class="text-blackey text-lg active:underline active:underline-offset-6 hover:underline hover:underline-offset-6 decoration-wavy decoration-1">BluePea</a>
          <a href="#team"
            class="text-blackey text-lg active:underline active:underline-offset-6 hover:underline hover:underline-offset-6 decoration-wavy decoration-1">Team</a>
          <button
            class="w-24 h-10 rounded-xl bg-primary text-lg shadow-hero-button hover:-translate-0.5 hover:shadow-hero-button-hover transition-all duration-50 cursor-pointer"
            onclick="window.open('https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A', '_blank')">
            Order
          </button>

        </div>
      </div>
    </div>

    <div class="fixed top-8 left-0 right-0 flex px-10 md:px-40 z-50 lg:hidden">
      <div
        class="container m-auto font-secondary backdrop-blur-[3px] bg-whitey/75 text-blackey flex justify-evenly py-4 px-4 rounded-full border border-blackey/10">
        <a href="#product"
          class="hover:font-bold active:font-bold hover:underline hover:underline-offset-4 decoration-wavy decoration-1 active:underline active:underline-offset-4">Product</a>
        <a href="#reason"
          class="hover:font-bold active:font-bold hover:underline hover:underline-offset-4 decoration-wavy decoration-1 active:underline active:underline-offset-4">BluePea</a>
        <a href="#team"
          class="hover:font-bold active:font-bold hover:underline hover:underline-offset-4 decoration-wavy decoration-1 active:underline active:underline-offset-4">Team</a>
      </div>
    </div>

    <!--  -->
    <div class="text-blackey font-secondary mt-20 lg:mt-28 flex">
      <div class="flex flex-col m-auto max-w-screen-sm lg:max-w-screen-lg w-full px-10 lg:px-40">
        <h2 class="font-primary mb-6 lg:mb-8 text-3xl lg:text-4xl font-semibold">The Story Behind Our
          <span class="bg-gradient-to-br from-primary to-secondary bg-clip-text text-transparent">Blue</span>
        </h2>
        <div class="text-sm lg:text-base flex flex-col leading-9 lg:leading-6 gap-3 lg:gap-6 text-justify">
          <p>We’re a group of university students who share one simple passion
            <span class=" font-semibold">"we love desserts, but we care about living healthy too".</span>
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

          <p>Each donut is made with <span class="font-semibold">natural
              ingredients</span> and colored with pure <span class="font-semibold">butterfly pea</span> extract.
            Every bite is a blend of soft texture, gentle herbal aroma,
            and natural sweetness.</p>
        </div>
      </div>
    </div>

    <!-- batch 1 -->
    <div
      class="w-full py-10 bg-primary bg-cover bg-center mt-20 lg:mt-32 relative font-secondary text-whitey flex flex-col items-center justify-center gap-12">
      <div class="bg-whitey h-20 w-0.5 absolute top-10 left-1/2 rounded-full xl:hidden"></div>
      <div class="bg-whitey h-0.5 w-74 md:w-96 absolute top-36 rounded-full xl:hidden"></div>

      <div class="bg-whitey h-20 w-0.5 absolute top-10 left-1/3 rounded-full hidden xl:block 2xl:hidden"></div>
      <div class="bg-whitey h-20 w-0.5 absolute top-10 right-1/3 rounded-full hidden xl:block 2xl:hidden"></div>


      <div class="flex h-full text-center w-full justify-center gap-16 md:gap-32">
        <div class="">
          <p class="text-6xl font-bold">35+</p>
          <p class="text-sm">Donuts Sold</p>
        </div>
        <div class="text-center hidden xl:block">
          <div class="flex justify-center items-center">
            <Icon icon="material-symbols:star-rounded" width="64" height="64" />
            <Icon icon="material-symbols:star-rounded" width="64" height="64" />
            <Icon icon="material-symbols:star-rounded" width="64" height="64" />
            <Icon icon="material-symbols:star-rounded" width="64" height="64" />
            <Icon icon="material-symbols:star-rounded" width="64" height="64" />
          </div>
          <p class="text-sm">5 Star Rating</p>
        </div>
        <div class="">
          <p class="text-6xl font-bold">15+</p>
          <p class="text-sm">Happy Customers</p>
        </div>
      </div>

      <div class="text-center xl:hidden">
        <div class="flex justify-center items-center">
          <Icon icon="material-symbols:star-rounded" width="64" height="64" />
          <Icon icon="material-symbols:star-rounded" width="64" height="64" />
          <Icon icon="material-symbols:star-rounded" width="64" height="64" />
          <Icon icon="material-symbols:star-rounded" width="64" height="64" />
          <Icon icon="material-symbols:star-rounded" width="64" height="64" />
        </div>
        <p class="text-sm">5 Star Rating</p>
      </div>
    </div>

    <!-- REVIEWWWWWWW -->
    <div class="flex flex-col mt-20">
      <p class="text-blackey text-center text-2xl mb-4">What Our Customer Says</p>

      <section class="container m-auto">
        <Swiper :modules="modules" :slides-per-view="1.5" :space-between="0" :loop="true" :free-mode="true"
          :speed="5000" :autoplay="{ delay: 0 }" :breakpoints="{
            768: {
              slidesPerView: 3
            },
            1024: {
              slidesPerView: 4
            },
            1280: {
              slidesPerView: 5
            },
            1536: {
              slidesPerView: 6
            }
          }">
          <SwiperSlide v-for="(review, index) in reviews.slice(0, 7)" :key="index" class="py-2">
            <div
              class="w-56 shadow border border-secondary/25 rounded-xl mt-4 text-blackey font-secondary text-sm flex flex-col p-4 gap-2">
              <div class="flex justify-between h-full">
                <p class="font-bold">{{ review.name }}</p>
                <div class="flex justify-center items-center">
                  <Icon icon="material-symbols:star-rounded" width="20" height="20" style="color: #95acf2"
                    v-for="(n, index) in 5" :key="index" />
                </div>
              </div>

              <p class="mt-4">{{ review.review }}</p>

              <p class="text-xs opacity-50">{{ review.variants }}</p>

            </div>
          </SwiperSlide>
        </Swiper>

        <Swiper :modules="modules" :slides-per-view="1.5" :space-between="0" :loop="true" :free-mode="true"
          :speed="5000" :autoplay="{ delay: 0, reverseDirection: true }" :breakpoints="{
            768: {
              slidesPerView: 3
            },
            1024: {
              slidesPerView: 4
            },
            1280: {
              slidesPerView: 5
            },
            1536: {
              slidesPerView: 6
            }
          }">
          <SwiperSlide v-for="(review, index) in reviews.slice(7)" :key="index" class="py-2">
            <div
              class="w-56 shadow border border-secondary/25 rounded-xl mt-4 text-blackey font-secondary text-sm flex flex-col p-4 gap-2">
              <div class="flex justify-between h-full">
                <p class="font-bold">{{ review.name }}</p>
                <div class="flex justify-center items-center">
                  <Icon icon="material-symbols:star-rounded" width="20" height="20" style="color: #95acf2"
                    v-for="(n, index) in 5" :key="index" />
                </div>
              </div>

              <p class="mt-4">{{ review.review }}</p>

              <p class="text-xs opacity-50">{{ review.variants }}</p>

            </div>
          </SwiperSlide>
        </Swiper>
      </section>
    </div>

    <!-- products header -->
    <div class="flex flex-col overflow-hidden">
      <h2 id="product"
        class="text-primary mx-auto text-4xl lg:text-6xl mt-32 scroll-mt-28 lg:scroll-mt-30 font-semibold lg:mt-40">Our
        Products
      </h2>

      <!-- container products -->
      <div class="max-w-screen-lg m-auto hidden lg:flex">

        <div
          class="mt-12 mx-10 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container">
          <div class="absolute inset-0 bg-[url('@/assets/pattern/linePattern.png')] bg-cover bg-bottom opacity-5 z-0">
          </div>

          <p class=" text-center font-secondary mt-10 text-5xl">All Variants only 7K</p>
          <div class="grid grid-cols-3 grid-rows-3 px-4 py-32 gap-y-36 gap-x-4 mt-4 mb-4">

            <p class="text-5xl self-center text-right row-start-1 col-start-1">Signature <br>Butterfly</p>
            <div class="col-span-1 bg-whitey rounded-2xl h-30 flex z-10 shadow-product-desc">
              <div class="text-primary font-secondary m-auto flex flex-col justify-center items-center gap-2 mr-12">
                <div class="text-2xl text-center leading-[1.75rem]">
                  Blue beauty with <span class="font-semibold">telang glaze</span> and <span
                    class="font-semibold">crumbs</span>
                </div>
              </div>
            </div>

            <div class="col-span-1 row-start-2 col-start-2 bg-whitey rounded-2xl h-30 flex z-10 shadow-product-desc">
              <div class="text-primary font-secondary m-auto flex flex-col justify-center items-center gap-2 ml-14">
                <div class="text-2xl text-center leading-[1.75rem]">
                  A classic <span class="font-semibold">matcha glazed</span> with grated and <span
                    class="font-semibold">almond</span>
                </div>
              </div>
            </div>
            <p class="text-5xl self-center row-start-2 col-start-3">Matcha <br>Butterfly</p>

            <p class="text-5xl self-center text-right row-start-3 col-start-1">Chocolate <br>Butterfly</p>
            <div class="col-span-1 row-start-3 col-start-2 bg-whitey rounded-2xl h-30 flex z-10 shadow-product-desc">
              <div
                class="text-secondary font-secondary m-auto flex flex-col justify-center items-center gap-2 mr-16 ml-2">
                <div class="text-2xl text-center leading-[1.75rem]">
                  Deep <span class="font-semibold">chocolate glazed</span> meets <span class="font-semibold">regal
                    crumbs</span>
                </div>
              </div>
            </div>

            <!-- gambar donut -->
            <img src="@/assets/img/donutSignature.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:rotate-6 hover:scale-105 hover:rotate-6 transition-all ease-in-out duration-750 top-32 right-16">
            <img src="@/assets/img/donutMatcha.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:-rotate-6 hover:scale-105 hover:-rotate-6 transition-all ease-in-out duration-750 top-100 left-16">
            <img src="@/assets/img/donutChoco.png" alt=""
              class="absolute aspect-auto w-80 z-40 cursor-default active:scale-105 active:-rotate-6 hover:scale-105 hover:-rotate-6 transition-all ease-in-out duration-750 bottom-8 right-16">

            <p class="absolute font-secondary bottom-5 left-10">*Available by pre-order only</p>
          </div>
        </div>

      </div>


      <!-- slider -->
      <section class="flex lg:hidden container m-auto">
        <Swiper :modules="[EffectCards]" :effect="'cards'" :grabCursor="true" class="w-72 md:w-md mt-8" :breakpoints="{
          768: {
            cardsEffect: {
              perSlideOffset: 10,
              perSlideRotate: 6
            },
          }
        }">
          <SwiperSlide class="relative bg-linear-to-br from-primary to-secondary rounded-4xl group">
            <div
              class="absolute inset-0 bg-[url('@/assets/pattern/linePattern.png')] bg-cover bg-bottom opacity-5 -z-10">
            </div>

            <div class="px-6 py-8 flex flex-col gap-4 md:gap-6 z-50">
              <p class="text-4xl text-center">Signature <br>Butterfly</p>

              <img src="@/assets/img/donutSignature.png" alt=""
                class="aspect-auto w-56 md:w-72 z-40 cursor-default group-active:rotate-4 group-hover:rotate-4 group-hover:scale-105 group-active:scale-105 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

              <p class="font-secondary text-center text-base">Topping: Telang crumbs</p>

              <p class="font-secondary text-center text-4xl mb-4 font-semibold">Only 7K</p>
            </div>

            <p class="absolute font-secondary text-xs bottom-3 md:bottom-4 left-4 md:left-6 font-light">*Available by pre-order only</p>
          </SwiperSlide>

          <SwiperSlide class="relative bg-linear-to-br from-primary to-secondary rounded-4xl group">
            <div
              class="absolute inset-0 bg-[url('@/assets/pattern/linePattern.png')] bg-cover bg-bottom opacity-5 -z-10">
            </div>

            <div class="px-6 py-8 flex flex-col gap-4 md:gap-6 z-10">
              <p class="text-4xl text-center">Matcha <br>Butterfly</p>

              <img src="@/assets/img/donutMatcha.png" alt=""
                class="aspect-auto w-56 md:w-72 z-40 cursor-default group-active:rotate-4 group-hover:rotate-4 group-hover:scale-105 group-active:scale-105 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

              <p class="font-secondary text-center text-base">Topping: Almond</p>

              <p class="font-secondary text-center text-4xl mb-4 font-semibold">Only 7K</p>
            </div>

            <p class="absolute font-secondary text-xs bottom-3 md:bottom-4 left-4 md:left-6 font-light">*Available by pre-order only</p>
          </SwiperSlide>

          <SwiperSlide class="relative bg-linear-to-br from-primary to-secondary rounded-4xl group">
            <div
              class="absolute inset-0 bg-[url('@/assets/pattern/linePattern.png')] bg-cover bg-bottom opacity-5 -z-10">
            </div>

            <div class="px-6 py-8 flex flex-col gap-4 md:gap-6 z-10">
              <p class="text-4xl text-center">Chocolate <br>Butterfly</p>

              <img src="@/assets/img/donutChoco.png" alt=""
                class="aspect-auto w-56 md:w-72 z-40 cursor-default group-active:rotate-4 group-hover:rotate-4 group-hover:scale-105 group-active:scale-105 transition-all ease-in-out duration-750 top-30 left-10 drop-shadow-md/25 self-center">

              <p class="font-secondary text-center text-base">Topping: Regal</p>

              <p class="font-secondary text-center text-4xl mb-4 font-semibold">Only 7K</p>
            </div>

            <p class="absolute font-secondary text-xs bottom-3 md:bottom-4 left-4 md:left-6 font-light">*Available by pre-order only</p>
          </SwiperSlide>
        </Swiper>
      </section>

      <!-- <button
        class="fixed w-32 md:w-46 h-12 md:h-18 rounded-xl lg:hidden border border-secondary bg-whitey font-bold text-base md:text-2xl bottom-8 right-8 animate-bounce font-secondary z-40 shadow-preorder-button leading-4 md:leading-6"
        onclick="window.open('https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A', '_blank')">
        <p class="text-secondary">Pre-order<br>just opened!</p>
      </button> -->

    </div>


    <!-- why choose us -->
    <div class=" bg-gradient-to-b from-whitey to-secondary mt-32 lg:mt-60 px-5 flex flex-col">
      <p id="reason"
        class="font-primary text-blackey text-center text-4xl lg:text-5xl font-semibold scroll-mt-28 lg:scroll-mt-30">
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
          <div
            class="absolute inset-0 bg-[url('@/assets/pattern/linePatternPurple.png')] bg-cover bg-center opacity-5 z-0">
          </div>
          <img src="@/assets/img/reasonHealthy.png" alt=""
            class="absolute aspect-auto w-20 -top-6 -right-8.5 rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="@/assets/img/reasonHealthy.png" alt=""
            class="absolute aspect-auto w-28 -top-6 -left-11 -rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Healthy <br>Indulgence</p>
          <p class=" text-center text-xs lg:text-sm z-10">Low sugar, preservative free, and made for a lighter treat
          </p>
        </div>

        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
          <div
            class="absolute inset-0 bg-[url('@/assets/pattern/linePatternPurple.png')] bg-cover bg-center opacity-5 z-0">
          </div>
          <img src="@/assets/img/reasonBlue.png" alt=""
            class="absolute aspect-auto w-20 -top-6 -left-7 -rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="@/assets/img/reasonBlue.png" alt=""
            class="absolute aspect-auto w-24 -top-9 -right-9 -rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Blue Magic <br>Aesthetic</p>
          <p class=" text-center text-xs lg:text-sm z-10">Naturally blue from butterfly pea extract, beautiful and
            beneficial</p>
        </div>

        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
          <div
            class="absolute inset-0 bg-[url('@/assets/pattern/linePatternPurple.png')] bg-cover bg-center opacity-5 z-0">
          </div>
          <img src="@/assets/img/reasonPrice.png" alt=""
            class="absolute aspect-auto w-24 -top-9 -right-8 rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="@/assets/img/reasonPrice.png" alt=""
            class="absolute aspect-auto w-30 -top-11 -left-16 -rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Student-Friendly <br>Price</p>
          <p class=" text-center text-xs lg:text-sm z-10">Premium quality that fits a student’s budget</p>
        </div>

        <!--  -->
        <div
          class="bg-whitey rounded-2xl py-6 px-6 flex flex-col gap-2 lg:gap-4 relative shadow-reasons active:shadow-reasons-hover active:-translate-0.5 hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default">
          <div
            class="absolute inset-0 bg-[url('@/assets/pattern/linePatternPurple.png')] bg-cover bg-center opacity-5 z-0">
          </div>
          <img src="@/assets/img/reasonLocal.png" alt=""
            class="absolute aspect-auto w-18 -top-4 -left-6 -rotate-12 drop-shadow-xs/50 lg:hidden">

          <img src="@/assets/img/reasonLocal.png" alt=""
            class="absolute aspect-auto w-22 -top-6 -right-6 rotate-12 drop-shadow-xs/50 hidden lg:block">

          <p class="font-bold text-center text-lg lg:text-xl leading-7 lg:leading-6">Local <br>Production</p>
          <p class=" text-center text-xs lg:text-sm z-10">Crafted by Indonesian students, made from local ingredients
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

        <img src="@/assets/img/donutLogo.svg" alt=""
          class="w-28 lg:w-40 absolute h-full animate-bounce transition-opacity duration-100 opacity-100 group-active:opacity-0 group-hover:opacity-0">

        <img src="@/assets/img/logoPurple.svg" alt=""
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
    <div class=" bg-gradient-to-b from-secondary to-primary pt-20 lg:pt-60 px-10 relative lg:flex lg:flex-col">

      <p id="team" class=" text-center text-3xl lg:text-4xl scroll-mt-28 lg:scroll-mt-30">The Sweet Souls Behind BluePea
        Bites</p>
      <p class=" text-center font-secondary text-sm lg:text-lg mt-2">Meet the team that makes BluePea Bites possible</p>

      <div
        class="lg:self-center grid grid-cols-2 grid-rows-3 grid-flow-row lg:grid-cols-6 lg:grid-rows-3 lg:grid-flow-col mt-10 gap-y-4 gap-x-2 font-secondary lg:max-w-screen-lg">

        <!--  -->
        <div
          class="flex flex-col lg:row-start-1 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="@/assets/img/gina.png" alt="" class="aspect-auto drop-shadow-profile w-30 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Gina</p>
          <p class="text-sm">Founder & General Coordinator</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-2 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="@/assets/img/sandra.png" alt="" class="aspect-auto drop-shadow-profile w-18 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Sandra</p>
          <p class="text-sm">Marketing & Social Media</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-1 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="@/assets/img/myBaddieGueh.png" alt="" class="aspect-auto drop-shadow-profile w-24 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Farah</p>
          <p class="text-sm">Finance & Administration</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-2 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="@/assets/img/rizka.png" alt="" class="aspect-auto drop-shadow-profile w-28 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Rizka</p>
          <p class="text-sm">Production Manager</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-1 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="@/assets/img/dini.png" alt="" class="aspect-auto drop-shadow-profile w-24 self-center">

          <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Dini</p>
          <p class="text-sm">Supply Chain & Logistics</p>
        </div>

        <!--  -->
        <div
          class="flex flex-col lg:row-start-2 lg:row-span-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-4 shadow-md/50 cursor-default hover:scale-y-105 lg:hover:scale-y-110 active:scale-y-105 hover:bg-secondary active:bg-secondary hover:text-whitey active:text-whitey hover:inset-ring-whitey active:inset-ring-whitey hover:inset-ring-2 active:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
          <img src="@/assets/img/cazie.png" alt="" class="aspect-auto drop-shadow-profile w-20 self-center">

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
            class="grow border-3 rounded-xl cursor-pointer h-14 lg:h-20 hover:bg-whitey active:bg-whitey group transition-all ease-in-out duration-100"
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

    <!-- promo pop up potrait -->
    <!-- <div id="promo-popup"
      class="fixed top-1/2 left-1/2 -translate-x-1/2 bg-whitey z-50 w-2/3 sm:w-1/2 md:w-2/5 lg:hidden rounded-2xl px-2 py-4 text-blackey font-secondary flex flex-col justify-center items-center gap-2 text-lg md:text-xl shadow-promo transition ease-in-out duration-2000"
      :class="showPopup ? '-translate-y-1/2 opacity-100' : 'translate-y-full opacity-0'">

      <h1 class="">Limited Promo</h1>
      <img src="@/assets/img/promo.jpg" alt="" class="rounded-xl">

      <div class="flex gap-4 mt-2">
        <button class="text-primary border border-primary px-6 py-1 rounded" @click="closePopup">Close</button>
        <button class="text-whitey bg-primary px-6 py-1 rounded"
          onclick="window.open('https://wa.me/6281220406031?text=FORMAT%20ORDER%20%E2%80%93%20Donat%20Sehat%20Bunga%20Telang%20Blue%20Pea%20Bites%0A%0AHai%2C%20terima%20kasih%20sudah%20tertarik%20dengan%20donat%20sehat%20kami!%0ASilakan%20isi%20format%20berikut%20untuk%20melakukan%20preorder%0A%0ADATA%20PEMESAN%0ANama%3A%0ANo.%20HP%20%2F%20WhatsApp%3A%0AAlamat%20Lengkap%3A%0AMetode%20Pengiriman%3A%20(Pick%20Up%20%2F%20Delivery)%3A%0A%0APILIHAN%20PRODUK%0A-%20Signature%20Butterfly%0A-%20Chocolate%20Butterfly%0A-%20Matcha%20Butterfly%0A%0AJumlah%20Pesanan%20dan%20Varian%20Rasanya%3A%0A%0AMETODE%20PEMBAYARAN%0ATransfer%20ke%3A%0A-%20BCA%0A5776396890%20an.%20Rizka%20Puspa%20Etsuno%0A-%20Gopay%0A087772839737%20an.%20Allysandra%20Rafeyfa%20A', '_blank')">Order</button>
      </div>
    </div> -->

  </div>
</template>

<style scoped>
.swiper-free-mode>.swiper-wrapper {
  transition-timing-function: linear !important;
}
</style>
