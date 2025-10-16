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
</script>

<template>
    <div class="font-primary box-border bg-whitey text-whitey">

        <!-- hero -->
        <div class="min-w-full min-h-screen bg-gradient-to-br from-secondary to-primary overflow-hidden flex relative">

            <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-top opacity-10 z-0"></div>

            <div class="max-w-screen-lg w-full m-auto flex justify-between opacity-100 z-10 px-6">
                <div class="my-auto flex flex-col gap-8">
                    <div>
                        <h1 class="text-whitey font-extrabold text-[6rem] leading-[6rem]">BluePea</h1>
                        <div class="flex">
                            <h1 class="text-whitey font-extrabold text-[6rem] leading-[6rem]">Bites</h1>
                            <img src="/img/donutLogo.svg" alt="" class="h-auto w-40">
                        </div>
                    </div>
                    <p class="font-secondary text-whitey text-3xl">Naturally Sweet, Beautifully Healthy</p>
                </div>
                <div class=" aspect-square w-md bg-[url('/img/donutMaskot.png')] bg-center bg-contain bg-no-repeat">
                </div>
            </div>

        </div>

        <!-- bar -->
        <div id="navbar-sentinel"></div>
        <div id="navbar" class="h-18 sticky top-0 flex bg-whitey z-50 mt-2 transition-all duration-1000 ease-in-out">
            <div class="max-w-screen-xl m-auto w-full flex justify-between px-10 font-secondary">
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
                        <a href="https://wa.me/628997065303" target="_blank">Order</a>
                    </button>
                </div>
            </div>
        </div>

        <div class="text-blackey font-secondary mt-40 flex">
            <div class="flex flex-col m-auto max-w-screen-xl w-full px-40">
                <h2 class="font-primary mb-14 text-5xl font-semibold">The Story Behind Our
                    <span class="bg-gradient-to-br from-primary to-secondary bg-clip-text text-transparent">Blue</span>
                </h2>
                <div class="text-xl flex flex-col leading-10 gap-6">
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
                            class="font-semibold text-5xl uppercase bg-secondary bg-clip-text text-transparent font-primary">Donut</span>
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
            <h2 id="product" class="text-primary mx-auto text-5xl mt-48 scroll-mt-30 font-semibold">Our Products</h2>

            <!-- container products -->
            <div
                class="mt-14 mx-40 rounded-4xl bg-gradient-to-b from-primary to-secondary relative overflow-hidden shadow-products-container">
                <div class="absolute inset-0 bg-[url('/pattern/linePattern.png')] bg-cover bg-bottom opacity-10 z-0">
                </div>

                <p class=" text-center font-secondary mt-10 text-5xl">All Variants only 7K</p>
                <div class="grid grid-cols-3 grid-rows-4 px-4 py-20 gap-y-30 gap-x-4">

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

                    <p class="text-5xl self-center text-right">Pandan <br>Butterfly</p>
                    <div class="col-span-2 bg-whitey rounded-2xl h-30 mr-40 flex z-10 shadow-product-desc">
                        <div
                            class="text-primary font-secondary m-auto pl-2 pr-44 flex flex-col justify-center items-center gap-2">
                            <div class="text-2xl text-center leading-[1.75rem]">
                                A classic Indonesian twist with grated <span class="font-semibold">coconut</span> and
                                <span class="font-semibold">chia</span>
                            </div>
                        </div>
                    </div>

                    <div class="col-span-2 bg-whitey rounded-2xl h-30 ml-40 flex z-10 shadow-product-desc">
                        <div
                            class="text-secondary font-secondary m-auto pr-4 pl-46 flex flex-col justify-center items-center gap-2">
                            <div class="text-2xl text-center leading-[1.75rem]">
                                Blue beauty with <span class="font-semibold">almond</span> and <span
                                    class="font-semibold">chia</span>
                                seed topping
                            </div>
                        </div>
                    </div>
                    <p class="text-5xl self-center">Signature <br>Butterfly</p>

                    <p class="text-5xl self-center text-right">Chocolate <br>Butterfly</p>
                    <div class="col-span-2 bg-whitey rounded-2xl h-30 mr-40 flex z-10 shadow-product-desc">
                        <div
                            class="text-secondary font-secondary m-auto pl-6 pr-47 flex flex-col justify-center items-center gap-2">
                            <div class="text-2xl text-center leading-[1.75rem]">
                                Deep <span class="font-semibold">chocolate</span> flavor meets <span
                                    class="font-semibold">butterfly
                                    pea</span>
                            </div>
                        </div>
                    </div>

                    <!-- gambar donut -->
                    <img src="/img/donut1.png" alt=""
                        class="absolute aspect-auto w-80 z-40 cursor-default hover:scale-105 hover:rotate-6 transition-all ease-in-out duration-750 top-30 left-10">
                    <img src="/img/donut2.png" alt=""
                        class="absolute aspect-auto w-80 z-40 cursor-default hover:scale-105 hover:-rotate-6 transition-all ease-in-out duration-750 top-90 right-10">
                    <img src="/img/donut3.png" alt=""
                        class="absolute aspect-auto w-80 z-40 cursor-default hover:scale-105 hover:rotate-6 transition-all ease-in-out duration-750 bottom-64 left-10">
                    <img src="/img/donut4.png" alt=""
                        class="absolute aspect-auto w-80 z-40 cursor-default hover:scale-105 hover:-rotate-6 transition-all ease-in-out duration-750 bottom-4 right-10">

                    <p class="absolute font-secondary bottom-5 left-10">*Available by pre-order only</p>
                </div>
            </div>
        </div>

        <!-- why choose us -->
        <div class=" bg-gradient-to-b from-whitey to-secondary mt-60">
            <p id="reason" class="font-primary text-blackey text-center text-6xl font-semibold scroll-mt-30">Why Choose
                BluePea Bites</p>
            <p class="font-secondary text-blackey text-center text-xl mt-4">Because our donuts are made not just to eat,
                but
                to enjoy with heart.</p>

            <div class="grid grid-cols-2 grid-rows-2 mx-80 mt-14 font-secondary text-blackey gap-8">
                <!--  -->
                <div
                    class="bg-whitey rounded-2xl py-6 px-8 flex flex-col gap-2 relative shadow-reasons hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
                    <div
                        class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
                    </div>
                    <img src="/img/reasonHealthy.png" alt=""
                        class="absolute aspect-auto w-26 -top-6 -right-10 rotate-12 drop-shadow-xs/50">

                    <p class="font-bold text-center text-xl leading-7">Healthy <br>Indulgence</p>
                    <p class=" text-justify text-sm z-10">Low sugar, preservative free, and baked for a lighter treat
                    </p>
                </div>

                <!--  -->
                <div
                    class="bg-whitey rounded-2xl py-6 px-8 flex flex-col gap-2 relative shadow-reasons hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
                    <div
                        class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
                    </div>
                    <img src="/img/reasonBlue.png" alt=""
                        class="absolute aspect-auto w-26 -top-8 -right-11 -rotate-12 drop-shadow-xs/50">

                    <p class="font-bold text-center text-xl leading-7">Blue Magic <br>Aesthetic</p>
                    <p class=" text-justify text-sm z-10">Naturally blue from butterfly pea extract, beautiful and
                        beneficial</p>
                </div>

                <!--  -->
                <div
                    class="bg-whitey rounded-2xl py-6 px-8 flex flex-col gap-2 relative shadow-reasons hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default hover:z-40">
                    <div
                        class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
                    </div>
                    <img src="/img/reasonPrice.png" alt=""
                        class="absolute aspect-auto w-30 -top-10 -right-10 rotate-12 drop-shadow-xs/50">

                    <p class="font-bold text-center text-xl leading-7">Student-Friendly <br>Price</p>
                    <p class=" text-justify text-sm z-10">Premium quality that fits a student’s budget</p>
                </div>

                <!--  -->
                <div
                    class="bg-whitey rounded-2xl py-6 px-8 flex flex-col gap-2 relative shadow-reasons hover:shadow-reasons-hover hover:-translate-0.5 transition-all ease-in-out duration-300 cursor-default">
                    <div
                        class="absolute inset-0 bg-[url('/pattern/linePatternPurple.png')] bg-cover bg-center opacity-10 z-0">
                    </div>
                    <img src="/img/reasonLocal.png" alt=""
                        class="absolute aspect-auto w-22 -top-5 -right-8 rotate-6 drop-shadow-xs/50">

                    <p class="font-bold text-center text-xl leading-7">Local <br>Production</p>
                    <p class=" text-justify text-sm z-10">Crafted by Indonesian students, made from local ingredients
                    </p>
                </div>
            </div>
        </div>


        <!-- bg biru bawah -->
        <div class="bg-secondary font-secondary flex flex-col items-center pt-60 gap-4">
            <div class=" flex flex-col text-center text-4xl gap-4">
                <p>If you can't wait to order,</p>
                <p>just <span class="font-primary text-6xl">BITES</span> this <span
                        class="font-primary text-6xl">DONUTS</span>
                </p>
            </div>
            <button
                class="h-60 w-full flex justify-center hover:bg-whitey transition-all ease-in-out duration-100 group relative cursor-pointer"
                onclick="window.open('https://wa.me/628997065303', '_blank')">

                <img src="/img/donutLogo.svg" alt=""
                    class="w-40 absolute h-full animate-bounce transition-opacity duration-100 opacity-100 group-hover:opacity-0">
                <img src="/img/logoPurple.svg" alt=""
                    class="w-40 absolute h-full animate-bounce transition-opacity duration-100 opacity-0 group-hover:opacity-100" />

                <p class="opacity-0 group-hover:opacity-100 duration-100 text-9xl font-primary text-primary m-auto">Hit
                    to</p>
                <p class="opacity-0 group-hover:opacity-100 duration-100 text-9xl font-primary text-primary m-auto">
                    Order</p>
            </button>
        </div>

        <!-- team -->
        <div class=" bg-gradient-to-b from-secondary to-primary pt-60 px-20 relative">

            <p id="team" class=" text-center text-4xl scroll-mt-30">The Sweet Souls Behind BluePea Bites</p>
            <p class=" text-center font-secondary text-xl mt-2">Meet the team that makes BluePea Bites possible</p>

            <div class="grid grid-cols-6 grid-rows-3 grid-flow-col mt-14 gap-2 font-secondary">

                <!--  -->
                <div
                    class="flex flex-col row-span-2 col-span-1 row-start-1 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-2 shadow-md/25 cursor-default hover:scale-y-120 hover:bg-secondary hover:text-whitey hover:inset-ring-whitey hover:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
                    <img src="/img/gina.png" alt="" class="aspect-auto drop-shadow-profile w-30 self-center">

                    <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Gina</p>
                    <p class="text-sm">Founder & General Coordinator</p>
                </div>

                <!--  -->
                <div
                    class="flex flex-col row-span-2 col-span-1 row-start-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-2 shadow-md/25 cursor-default hover:scale-y-120 hover:bg-secondary hover:text-whitey hover:inset-ring-whitey hover:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
                    <img src="/img/sandra.png" alt="" class="aspect-auto drop-shadow-profile w-18 self-center">

                    <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Sandra
                    </p>
                    <p class="text-sm">Marketing & Social Media</p>
                </div>

                <!--  -->
                <div
                    class="flex flex-col row-span-2 col-span-1 row-start-1 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-2 shadow-md/25 cursor-default hover:scale-y-120 hover:bg-secondary hover:text-whitey hover:inset-ring-whitey hover:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
                    <img src="/img/myBaddieGueh.png" alt="" class="aspect-auto drop-shadow-profile w-24 self-center">

                    <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Farah
                    </p>
                    <p class="text-sm">Finance & Administration</p>
                </div>

                <!--  -->
                <div
                    class="flex flex-col row-span-2 col-span-1 row-start-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-2 shadow-md/25 cursor-default hover:scale-y-120 hover:bg-secondary hover:text-whitey hover:inset-ring-whitey hover:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
                    <img src="/img/rizka.png" alt="" class="aspect-auto drop-shadow-profile w-28 self-center">

                    <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Rizka
                    </p>
                    <p class="text-sm">Production Manager</p>
                </div>

                <!--  -->
                <div
                    class="flex flex-col row-span-2 col-span-1 row-start-1 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-2 shadow-md/25 cursor-default hover:scale-y-120 hover:bg-secondary hover:text-whitey hover:inset-ring-whitey hover:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
                    <img src="/img/dini.png" alt="" class="aspect-auto drop-shadow-profile w-24 self-center">

                    <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Dini</p>
                    <p class="text-sm">Supply Chain & Logistics</p>
                </div>

                <!--  -->
                <div
                    class="flex flex-col row-span-2 col-span-1 row-start-2 bg-whitey rounded-2xl text-blackey justify-center px-6 py-4 text-center gap-2 shadow-md/25 cursor-default hover:scale-y-120 hover:bg-secondary hover:text-whitey hover:inset-ring-whitey hover:inset-ring-2 inset-ring-0 transition-all ease-in-out duration-150">
                    <img src="/img/cazie.png" alt="" class="aspect-auto drop-shadow-profile w-20 self-center">

                    <p class=" font-semibold text-lg underline decoration-wavy decoration-1 underline-offset-6">Cazie
                    </p>
                    <p class="text-sm">Customer Service & Sales</p>
                </div>

            </div>
        </div>

        <div class="bg-primary pt-60 text-right px-40 pb-80">
            <p class=" text-6xl font-semibold mb-2">Ready for Your First Bite?</p>
            <p class=" font-secondary mb-14 text-2xl">We open pre-orders only on weekend</p>

            <div class="flex font-secondary text-2xl gap-10">
                <button
                    class="grow ring rounded-xl cursor-pointer h-20 hover:bg-whitey group transition-all ease-in-out duration-100"
                    onclick="window.open('https://wa.me/628997065303', '_blank')">
                    <span
                        class="group-hover:bg-gradient-to-br group-hover:from-primary group-hover:to-secondary group-hover:bg-clip-text group-hover:text-transparent transition-all ease-out duration-1000 dura">Bites
                        First, Think Later</span>
                </button>
            </div>
        </div>

        <!--  -->
        <div class="w-full h-full bg-whitey font-secondary text-blackey py-6 px-10">
            <div class="flex justify-between text-sm">
                <div class="flex flex-col gap-4">
                    <div>
                        <p class="font-bold">Location</p>
                        <a href="https://maps.app.goo.gl/5wY1twKtwNs1nKKo8" target="_blank" rel="noopener noreferrer"
                            class="flex items-center gap-2 hover:underline decoration-wavy decoration-1 underline-offset-2">
                            <span class="icon-[mdi--map-marker] scale-150"></span>
                            <p>Jatinangor</p>
                        </a>
                    </div>

                    <div>
                        <p class="font-bold">Contact</p>
                        <a href="mailto:bluepeabites@gmail.com" target="_blank"
                            class="flex items-center gap-2 hover:underline decoration-wavy decoration-1 underline-offset-2">
                            <span class="icon-[ic--baseline-email] scale-125 cursor-pointer"></span>
                            <p>bluepeabites@gmail.com</p>
                        </a>
                        <a href="https://instagram.com/bluepeabites" target="_blank" rel="noopener noreferrer"
                            class="flex items-center gap-2 hover:underline decoration-wavy decoration-1 underline-offset-2">
                            <span class="icon-[mdi--instagram] scale-125 cursor-pointer"></span>
                            <p>@bluepeabites</p>
                        </a>
                        <a href="https://wa.me/628997065303" target="_blank" rel="noopener noreferrer"
                            class="flex items-center gap-2 hover:underline decoration-wavy decoration-1 underline-offset-2">
                            <span class="icon-[ic--baseline-whatsapp] scale-125 cursor-pointer"></span>
                            <p>0899-7065-303</p>
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
