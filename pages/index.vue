<template>
  <section class="main bg-gray-100">
    <Container class="py-5">
      <div
        class="p-5 flex justify-between bg-white border-2 border-gray-300 rounded-lg"
      >
        <div class="h6">
          <div class="font-normal text-gray-600 w-[300px] flex flex-col gap-1">
            <div class="h6 bg-secondary p-3 rounded-lg">
              <h6>Automobiles</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Clothes and wear</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Home interiors</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Computer and tech</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Tools, equipments</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Sports and outdoor</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Animal and pets</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>Machinery tools</h6>
            </div>

            <div class="p-3 rounded-lg">
              <h6>More category</h6>
            </div>
          </div>
        </div>

        <div class="flex-grow bg-slate-300 mx-5 relative">
          <img
            class="w-full h-[420px] object-cover"
            src="/images/bg-image-1.png"
            alt=""
          />

          <div class="h2 absolute top-16 left-12">
            <h2 class="font-normal">Latest trending</h2>
            <h2>Electronic items</h2>

            <button class="h6 bg-white px-4 py-3 rounded-lg mt-5">
              <h6>Learn more</h6>
            </button>
          </div>
        </div>

        <div class="w-[200px]">
          <div class="bg-secondary rounded-lg p-3 mb-5">
            <div class="h6 flex items-center gap-2">
              <img src="/icons/avatar.svg" alt="" />

              <div class="font-normal">
                <h6>Hi, user</h6>
                <h6>let's get started</h6>
              </div>
            </div>

            <div class="body-sm font-medium">
              <button class="w-full py-2 rounded-lg text-white bg-primary mt-4">
                <span>Join now</span>
              </button>

              <button
                class="w-full py-2 rounded-lg bg-white text-primary mt-4 border-2 border-gray-300"
              >
                <span>Log in</span>
              </button>
            </div>
          </div>

          <div class="h6 bg-orange rounded-lg p-5 pr-11 mb-5">
            <h6 class="text-white font-normal">
              Get US $10 off with a new supplier
            </h6>
          </div>

          <div class="h6 bg-[#55BDC3] rounded-lg p-5 pr-11">
            <h6 class="text-white font-normal">
              Send quotes with supplier preferences
            </h6>
          </div>
        </div>
      </div>

      <div
        class="my-5 flex bg-white border-2 border-gray-300 rounded-lg overflow-hidden"
      >
        <div class="p-5">
          <div class="h6">
            <h4 class="h4">Deals and offers</h4>
            <h6 class="font-normal text-gray-500">Hygiene equipments</h6>
          </div>

          <div class="mt-5 flex gap-2">
            <div class="h6 w-[50px] p-3 text-center bg-gray-600 rounded-lg">
              <h6 class="text-white">04</h6>
              <p class="body-mc">
                <span class="text-white font-normal">Day</span>
              </p>
            </div>

            <div class="h6 w-[50px] p-3 text-center bg-gray-600 rounded-lg">
              <h6 class="text-white">13</h6>
              <p class="body-mc">
                <span class="text-white font-normal">Hour</span>
              </p>
            </div>

            <div class="h6 w-[50px] p-3 text-center bg-gray-600 rounded-lg">
              <h6 class="text-white">34</h6>
              <p class="body-mc">
                <span class="text-white font-normal">Min</span>
              </p>
            </div>

            <div class="h6 w-[50px] p-3 text-center bg-gray-600 rounded-lg">
              <h6 class="text-white">56</h6>
              <p class="body-mc">
                <span class="text-white font-normal">Sec</span>
              </p>
            </div>
          </div>
        </div>

        <div
          v-for="(el, ind) in offers"
          :key="ind"
          class="border-l-2 border-gray-300 p-5"
        >
          <img
            class="w-[225px] h-[225px] object-cover"
            :src="`/images/${el.image}`"
            alt="offer"
          />

          <div class="text-center">
            <h5 class="h5 my-3">
              <span class="font-normal">{{ el.name }}</span>
            </h5>

            <h6
              class="h6 inline-block text-red bg-[#FFE3E3] px-3 py-2 rounded-full"
            >
              <span class="font-medium">{{ el.offer }}</span>
            </h6>
          </div>
        </div>
      </div>

      <div
        class="my-5 flex bg-white border-2 border-y border-gray-300 rounded-lg overflow-hidden"
      >
        <div class="flex-shrink-0 bg-slate-300 relative">
          <img
            class="w-[300px] h-[300px] object-cover"
            src="/images/bg-image-2.png"
            alt=""
          />

          <div class="h4 absolute top-8 left-8">
            <h4 class="w-[160px]">Home and outdoor</h4>

            <button class="h6 bg-white px-4 py-3 rounded-lg mt-5">
              <h6>Source now</h6>
            </button>
          </div>
        </div>

        <div class="w-full grid grid-cols-4">
          <div
            v-for="(el, ind) in home"
            :key="ind"
            class="border-l-2 border-y border-gray-300 p-5 relative"
          >
            <img
              class="w-[82px] h-[82px] object-cover absolute bottom-1 right-1"
              :src="`/images/${el.image}`"
              alt="home"
            />

            <div class="">
              <h6 class="h6 mb-3">
                <span class="font-normal">{{ el.name }}</span>
              </h6>

              <div class="body-sm-muted">
                <p>From</p>
                <p>USD {{ el.price }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div
        class="my-5 flex bg-white border-2 border-y border-gray-300 rounded-lg overflow-hidden"
      >
        <div class="flex-shrink-0 bg-slate-300 relative">
          <img
            class="w-[300px] h-[300px] object-cover"
            src="/images/bg-image-3.png"
            alt=""
          />

          <div class="h4 absolute top-8 left-8">
            <h4 class="w-[160px]">Consumer electronics and gadgets</h4>

            <button class="h6 bg-white px-4 py-3 rounded-lg mt-5">
              <h6>Source now</h6>
            </button>
          </div>
        </div>

        <div class="w-full grid grid-cols-4">
          <div
            v-for="(el, ind) in gadget"
            :key="ind"
            class="border-l-2 border-y border-gray-300 p-5 relative"
          >
            <img
              class="w-[82px] h-[82px] object-cover absolute bottom-1 right-1"
              :src="`/images/${el.image}`"
              alt="gadget"
            />

            <div class="">
              <h6 class="h6 mb-3">
                <span class="font-normal">{{ el.name }}</span>
              </h6>

              <div class="body-sm-muted">
                <p>From</p>
                <p>USD {{ el.price }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
const gadget = ref([
  { image: "gadget-image-1.png", name: "Smart watches", price: 19 },
  { image: "gadget-image-2.png", name: "Cameras", price: 89 },
  { image: "gadget-image-3.png", name: "Headphones", price: 10 },
  { image: "gadget-image-4.png", name: "Smart watches", price: 90 },
  { image: "gadget-image-5.png", name: "Gaming set", price: 35 },
  { image: "gadget-image-6.png", name: "Laptops & PC", price: 340 },
  { image: "gadget-image-7.png", name: "Smartphones", price: 19 },
  { image: "gadget-image-8.png", name: "Electric kattle", price: 240 },
]);

const home = ref([
  { image: "home-image-1.png", name: "Soft chairs", price: 19 },
  { image: "home-image-2.png", name: "Sofa & chair", price: 19 },
  { image: "home-image-3.png", name: "Kitchen dishes", price: 19 },
  { image: "home-image-4.png", name: "Smart watches", price: 19 },
  { image: "home-image-5.png", name: "Kitchen mixer", price: 100 },
  { image: "home-image-6.png", name: "Blenders", price: 39 },
  { image: "home-image-7.png", name: "Home appliance", price: 19 },
  { image: "home-image-8.png", name: "Coffee maker", price: 10 },
]);

const offers = ref([
  { image: "offer-image-1.png", name: "Smart watches", offer: "-25%" },
  { image: "offer-image-2.png", name: "Laptops", offer: "-15%" },
  { image: "offer-image-3.png", name: "GoPro cameras", offer: "-40%" },
  { image: "offer-image-4.png", name: "Headphones", offer: "-25%" },
  { image: "offer-image-5.png", name: "Canon camreras", offer: "-25%" },
]);

const isOpen = ref(false);

const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style lang="scss" scoped></style>
