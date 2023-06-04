<template>
  <section class="main bg-gray-100">
    <Container class="py-5">
      <div
        class="2xl:p-5 2xl:flex justify-between overflow-hidden bg-white border-2 border-gray-300 rounded-lg"
      >
        <div
          class="w-full 2xl:w-[300px] grid 2xl:flex auto-cols-max 2xl:flex-col grid-flow-col gap-2 2xl:gap-1 p-5 2xl:p-0 overflow-scroll 2xl:overflow-hidden"
        >
          <div v-for="(el, ind) in nav">
            <nuxt-link :to="el.link"
              ><div class="bg-gray-200 p-3 rounded-lg">
                <h6 class="h6">
                  <span class="font-normal text-primary">{{ el.name }}</span>
                </h6>
              </div></nuxt-link
            >
          </div>
        </div>

        <div class="flex-grow bg-slate-300 2xl:mx-5 relative">
          <img
            class="w-full h-[180px] 2xl:h-[420px] object-cover"
            src="/images/bg-image-1.png"
            alt=""
          />

          <div class="h5 2xl:h2 absolute top-8 2xl:top-16 left-6 2xl:left-12">
            <h2 class="font-normal">Latest trending</h2>
            <h2>Electronic items</h2>

            <button class="h6 bg-white px-4 py-3 rounded-lg mt-5">
              <h6 class="text-primary 2xl:text-dark">Learn more</h6>
            </button>
          </div>
        </div>

        <div class="w-[200px] hidden 2xl:block">
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
        class="my-5 2xl:flex bg-white border-2 border-gray-300 rounded-lg overflow-hidden"
      >
        <div
          class="px-2 py-5 2xl:p-5 flex items-center justify-between 2xl:block"
        >
          <div class="h6 h-[30px] 2xl:h-auto">
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

            <div
              class="h6 w-[50px] p-3 text-center bg-gray-600 rounded-lg hidden 2xl:block"
            >
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

        <div class="flex overflow-scroll 2xl:overflow-hidden">
          <div
            v-for="(el, ind) in offers"
            :key="ind"
            class="border-2 2xl:border-0 2xl:border-l-2 border-gray-300 p-5"
          >
            <div class="w-[130px] 2xl:w-auto flex justify-center 2xl:block">
              <img
                class="w-[100px] 2xl:w-[225px] h-[100px] 2xl:h-[225px] object-cover"
                :src="`/images/${el.image}`"
                alt="offer"
              />
            </div>

            <div class="text-center">
              <h5 class="body-sm 2xl:h5 my-3">
                <span class="text-dark 2xl:font-normal">{{ el.name }}</span>
              </h5>

              <h6
                class="h6 inline-block text-red bg-[#FFE3E3] px-3 py-2 rounded-full"
              >
                <span class="font-medium">{{ el.offer }}</span>
              </h6>
            </div>
          </div>
        </div>
      </div>

      <h3 class="h3 my-5 px-5 2xl:hidden"><span>Home and outdoor</span></h3>

      <div
        class="my-5 flex bg-white border-2 border-y border-gray-300 rounded-lg overflow-hidden"
      >
        <div class="hidden 2xl:block flex-shrink-0 bg-slate-300 relative">
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

        <div
          class="w-full flex 2xl:grid 2xl:grid-cols-4 overflow-scroll 2xl:overflow-hidden"
        >
          <div
            v-for="(el, ind) in home"
            :key="ind"
            class="border-2 2xl:border-l-2 2xl:border-y 2xl:border-r-0 border-gray-300 p-5 relative"
          >
            <div
              class="w-[100px] 2xl:w-auto flex justify-center 2xl:block 2xl:absolute 2xl:bottom-1 2xl:right-1 mb-3 2xl:mb-0"
            >
              <img
                class="w-[82px] h-[82px] object-cover"
                :src="`/images/${el.image}`"
                alt="gadget"
              />
            </div>

            <div class="text-center 2xl:text-start">
              <h6 class="body-sm 2xl:h6 mb-3">
                <span class="2xl:font-normal">{{ el.name }}</span>
              </h6>

              <h6 class="body-mc-muted">
                <span
                  >From <br class="hidden 2xl:block" />
                  USD {{ el.price }}</span
                >
              </h6>
            </div>
          </div>
        </div>
      </div>

      <button
        class="h6 bg-white mx-3 px-5 py-3 rounded-lg 2xl:hidden flex gap-3 items-center"
      >
        <h6 class="text-primary">Source now</h6>

        <Icons name="arrow_forward" color="#0D6EFD" />
      </button>

      <h3 class="h3 my-5 px-5 2xl:hidden"><span>Consumer electronics</span></h3>

      <div
        class="my-5 flex bg-white border-2 border-y border-gray-300 rounded-lg overflow-hidden"
      >
        <div class="hidden 2xl:block flex-shrink-0 bg-slate-300 relative">
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

        <div
          class="w-full flex 2xl:grid 2xl:grid-cols-4 overflow-scroll 2xl:overflow-hidden"
        >
          <div
            v-for="(el, ind) in gadget"
            :key="ind"
            class="border-2 2xl:border-l-2 2xl:border-y 2xl:border-r-0 border-gray-300 p-5 relative"
          >
            <div
              class="w-[100px] 2xl:w-auto flex justify-center 2xl:block 2xl:absolute 2xl:bottom-1 2xl:right-1 mb-3 2xl:mb-0"
            >
              <img
                class="w-[82px] h-[82px] object-cover"
                :src="`/images/${el.image}`"
                alt="gadget"
              />
            </div>

            <div class="text-center 2xl:text-start">
              <h6 class="body-sm 2xl:h6 mb-3">
                <span class="2xl:font-normal">{{ el.name }}</span>
              </h6>

              <h6 class="body-mc-muted">
                <span
                  >From <br class="hidden 2xl:block" />
                  USD {{ el.price }}</span
                >
              </h6>
            </div>
          </div>
        </div>
      </div>

      <button
        class="h6 bg-white mx-3 px-5 py-3 rounded-lg 2xl:hidden flex gap-3 items-center"
      >
        <h6 class="text-primary">Source now</h6>

        <Icons name="arrow_forward" color="#0D6EFD" />
      </button>

      <div
        class="my-5 flex bg-white border-2 border-gray-300 rounded-lg overflow-hidden"
      >
        <div class="flex-shrink-0 bg-slate-300 relative">
          <img
            class="w-full h-[150px] 2xl:h-[500px] object-cover"
            src="/images/bg-image-4.png"
            alt=""
          />

          <div class="cover w-full h-full absolute top-0 z-10"></div>

          <div
            class="absolute w-[210px] 2xl:w-[400px] top-6 2xl:top-12 left-6 2xl:left-10 z-20"
          >
            <h2 class="h5 2xl:h2 mb-4 2xl:mb-5">
              <span class="text-white"
                >An easy way to send requests to all suppliers</span
              >
            </h2>

            <h6 class="body hidden 2xl:block">
              <span class="text-white font-normal">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
                eiusmod tempor incididunt.</span
              >
            </h6>

            <button
              class="2xl:hidden absolute px-3 2xl:px-4 py-2 2xl:py-3 bg-primary rounded-lg"
            >
              <span class="text-white font-medium"> Send inquiry </span>
            </button>
          </div>

          <div
            class="absolute w-0 2xl:w-[500px] top-12 right-10 z-20 bg-white rounded-lg 2xl:p-8"
          >
            <div class="">
              <h4 class="h4 mb-5">
                <span class="">Send quote to suppliers</span>
              </h4>

              <div class="h6">
                <input
                  type="text"
                  name="name"
                  id="name"
                  placeholder="What item you need?"
                  class="font-normal border-2 border-gray-300 rounded-lg p-2 w-full mb-5"
                />

                <div class="relative w-full mb-5">
                  <!-- <Icons
                  class="absolute bottom-0 -right-1 rotate-45"
                  name="arrow_right"
                  color="#E4E4E4"
                /> -->
                  <textarea
                    name="details"
                    id="details"
                    rows="3"
                    class="font-normal border-2 border-gray-300 rounded-lg p-2 w-full max-h-[100px] min-h-[50px]"
                    placeholder="Type more details"
                  ></textarea>
                </div>

                <div class="flex gap-5 items-center mb-5">
                  <input
                    type="number"
                    placeholder="Quantity"
                    class="font-normal border-2 border-gray-300 rounded-lg p-2 w-[200px]"
                  />

                  <div class="relative">
                    <Icons
                      class="absolute top-[25%] right-2"
                      name="expand_more"
                      color="#8B96A5"
                    />
                    <select
                      name="pcs"
                      id="pcs"
                      class="font-normal border-2 border-gray-300 rounded-lg p-2 w-[150px] appearance-none"
                    >
                      <option selected hidden disabled>Pcs</option>
                      <option>item 1</option>
                      <option>item 2</option>
                      <option>item 3</option>
                    </select>
                  </div>
                </div>
              </div>

              <button class="px-4 py-3 bg-primary rounded-lg">
                <span class="text-white font-medium"> Send inquiry </span>
              </button>
            </div>
          </div>
        </div>
      </div>

      <div class="px-5 2xl:p-0">
        <h3 class="h3 my-5 2xl:my-10"><span>Recommended items</span></h3>

        <div class="grid 2xl:grid-cols-5 grid-cols-2 gap-5">
          <div
            v-for="(el, ind) in recommend"
            :key="ind"
            class="p-5 bg-white border-2 border-gray-300 rounded-lg overflow-hidden"
          >
            <img
              class="w-[150px] h-[150px] 2xl:w-[200px] 2xl:h-[200px] object-cover mb-3 2xl:mb-5"
              :src="`/images/${el.image}`"
              alt="rec"
            />

            <h6 class="h6 mb-1 2xl:mb-3">
              <span>${{ el.price }}</span>
            </h6>

            <h6 class="body-muted">
              <span>{{ el.description }}</span>
            </h6>
          </div>
        </div>
      </div>

      <h3 class="h3 my-10 2xl:block hidden"><span>Our extra services</span></h3>

      <div class="2xl:block hidden">
        <div class="grid grid-cols-4 gap-5">
          <div
            v-for="(el, ind) in service"
            :key="ind"
            class="bg-white border-2 border-gray-300 rounded-lg overflow-hidden"
          >
            <div class="relative">
              <div
                class="w-full h-full bg-black top-0 absolute opacity-40"
              ></div>

              <img
                class="w-full h-[150px] object-cover"
                :src="`/images/${el.image}`"
                alt="service"
              />

              <div
                class="absolute -bottom-8 right-5 rounded-full p-5 border-[3px] border-white bg-secondary"
              >
                <Icons :name="el.icon" color="#1C1C1C" />
              </div>
            </div>

            <div class="p-5 w-[240px]">
              <h5 class="h5">
                <span>{{ el.name }}</span>
              </h5>
            </div>
          </div>
        </div>
      </div>

      <h3 class="h3 my-10 2xl:block hidden">
        <span>Suppliers by region</span>
      </h3>

      <div class="2xl:grid 2xl:grid-cols-5 2xl:gap-5 hidden">
        <div
          v-for="(el, ind) in region"
          :key="ind"
          class="flex items-center gap-3"
        >
          <img
            class="w-[35px] h-[25px] object-cover"
            :src="`/images/${el.image}`"
            alt="reg"
          />

          <div>
            <h6 class="h6">
              <span class="font-medium">{{ el.name }}</span>
            </h6>

            <h6 class="body-sm-muted">
              <span>{{ el.site }}</span>
            </h6>
          </div>
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
const nav = ref([
  {
    id: 1,
    name: "Automobiles",
    link: "/",
  },
  {
    id: 2,
    name: "Clothes and wear",
    link: "/",
  },
  {
    id: 3,
    name: "Home interiors",
    link: "/",
  },
  {
    id: 4,
    name: "Computer and tech",
    link: "/mobile",
  },
  {
    id: 5,
    name: "Tools, equipments",
    link: "/",
  },
  {
    id: 6,
    name: "Sports and outdoor",
    link: "/",
  },
  {
    id: 7,
    name: "Animal and pets",
    link: "/",
  },
  {
    id: 8,
    name: "Machinery tools",
    link: "/",
  },
  {
    id: 9,
    name: "More category",
    link: "/",
  },
]);

const region = ref([
  { image: "ae.png", name: "Arabic Emirates", site: "shopname.ae" },
  { image: "au.png", name: "Australia", site: "shopname.au" },
  { image: "us.png", name: "United States", site: "shopname.us" },
  { image: "ru.png", name: "Russia", site: "shopname.ru" },
  { image: "it.png", name: "Italy", site: "shopname.it" },
  { image: "dk.png", name: "Denmark", site: "shopname.com.dk" },
  { image: "fr.png", name: "France", site: "shopname.com.fr" },
  { image: "ae.png", name: "Arabic Emirates", site: "shopname.ae" },
  { image: "cn.png", name: "China", site: "shopname.cn" },
  { image: "gb.png", name: "Great Britain", site: "shopname.co.uk" },
]);

const service = ref([
  {
    image: "service-image-1.png",
    icon: "search",
    name: "Source from Industry Hubs",
  },
  {
    image: "service-image-2.png",
    icon: "inventory_2",
    name: "Customize Your Products",
  },
  {
    image: "service-image-3.png",
    icon: "send",
    name: "Fast, reliable shipping by ocean or air",
  },
  {
    image: "service-image-4.png",
    icon: "security",
    name: "Product monitoring and inspection",
  },
]);

const recommend = ref([
  {
    image: "rec-image-1.png",
    description: "T-shirts with multiple colors, for men",
    price: 10.3,
  },
  {
    image: "rec-image-2.png",
    description: "Jeans shorts for men blue color",
    price: 10.3,
  },
  {
    image: "rec-image-3.png",
    description: "Brown winter coat medium size",
    price: 12.5,
  },
  {
    image: "rec-image-4.png",
    description: "Jeans bag for travel for men",
    price: 34.0,
  },
  { image: "rec-image-5.png", description: "Leather wallet", price: 99.0 },
  {
    image: "rec-image-6.png",
    description: "Canon camera black, 100x zoom",
    price: 9.99,
  },
  {
    image: "rec-image-7.png",
    description: "Headset for gaming with mic",
    price: 8.99,
  },
  {
    image: "rec-image-8.png",
    description: "Smartwatch silver color modern",
    price: 10.3,
  },
  {
    image: "rec-image-9.png",
    description: "Blue wallet for men leather metarfial",
    price: 10.3,
  },
  {
    image: "rec-image-10.png",
    description: "Jeans bag for travel for men",
    price: 80.95,
  },
]);

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

<style lang="scss" scoped>
.cover {
  background: linear-gradient(
    94.99deg,
    #2c7cf1 7.19%,
    rgba(0, 209, 255, 0.5) 89.49%
  );
}
</style>
