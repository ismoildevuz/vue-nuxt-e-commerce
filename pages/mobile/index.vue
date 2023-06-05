<template>
  <section class="mobile bg-gray-100 min-h-[1500px]">
    <Container>
      <div
        class="w-full grid 2xl:hidden auto-cols-max grid-flow-col gap-2 p-5 overflow-scroll"
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

      <div class="hidden py-5 2xl:flex gap-2 body-muted">
        <span>Home</span>
        <Icons name="chevron_right" color="#8B96A5" />
        <span>Clothings</span>
        <Icons name="chevron_right" color="#8B96A5" />
        <span>Men’s wear</span>
        <Icons name="chevron_right" color="#8B96A5" />
        <span>Summer clothing</span>
      </div>

      <div class="2xl:flex">
        <div class="hidden 2xl:block 2xl:w-[250px] 2xl:flex-shrink-0">
          <div
            v-for="(el, ind) in filter"
            :key="ind"
            class="border-t-2 border-gray-300 mx-3 select-none"
          >
            <div
              @click="el.isOpen = !el.isOpen"
              class="flex items-center justify-between py-3 cursor-pointer"
            >
              <h6 class="h6">
                <span>{{ el.name }}</span>
              </h6>

              <Icons
                :name="el.isOpen ? 'expand_less' : 'expand_more'"
                color="#8B96A5"
              />
            </div>

            <div v-if="el.isOpen" class="mb-5 body">
              <div
                v-for="(item, index) in el.items"
                :key="index"
                class="flex items-center gap-2 py-[6px]"
              >
                <input
                  v-show="el.type == 'checkbox'"
                  type="checkbox"
                  v-model="item.checked"
                />
                <h6>
                  <span>{{ item.name }}</span>
                </h6>
              </div>

              <div class="flex items-center justify-between py-[6px]">
                <h6><span class="text-primary">See all</span></h6>
              </div>
            </div>
          </div>
        </div>

        <div class="w-full 2xl:px-5 max-w-[1150px]">
          <div
            class="bg-white border-y-2 2xl:border-2 border-gray-300 2xl:rounded-lg py-3 px-5 2xl:p-3 flex items-center justify-between w-full"
          >
            <div class="hidden 2xl:block">
              <h6 class="h6">
                <span class="font-normal">{{ items }} items in </span
                ><span> {{ page }}</span>
              </h6>
            </div>

            <div
              class="flex items-center justify-between w-full 2xl:w-auto 2xl:justify-center 2xl:gap-4"
            >
              <div class="hidden 2xl:flex gap-3">
                <input type="checkbox" />
                <h6 class="h6">
                  <span class="font-normal">Verified only</span>
                </h6>
              </div>

              <div class="relative hidden 2xl:block">
                <Icons
                  class="absolute top-[25%] right-2"
                  name="expand_more"
                  color="#8B96A5"
                />
                <select
                  name="pcs"
                  id="pcs"
                  class="font-normal border-2 border-gray-300 rounded-lg p-2 w-[200px] appearance-none"
                >
                  <option selected hidden disabled>Featured</option>
                  <option>item 1</option>
                  <option>item 2</option>
                  <option>item 3</option>
                </select>
              </div>

              <div class="relative 2xl:hidden">
                <Icons
                  class="absolute top-[15%] 2xl:top-[25%] right-2"
                  name="sort"
                  color="#8B96A5"
                />
                <select
                  name="pcs"
                  id="pcs"
                  class="font-normal border-2 border-gray-300 rounded-lg p-1 2xl:p-2 w-[140px] 2xl:w-[200px] appearance-none"
                >
                  <option selected hidden disabled>Sort: Newest</option>
                  <option>item 1</option>
                  <option>item 2</option>
                  <option>item 3</option>
                </select>
              </div>

              <div class="relative 2xl:hidden">
                <Icons
                  class="absolute top-[15%] 2xl:top-[25%] right-2"
                  name="filter_alt"
                  color="#8B96A5"
                />
                <select
                  name="pcs"
                  id="pcs"
                  class="font-normal border-2 border-gray-300 rounded-lg p-1 2xl:p-2 w-[110px] 2xl:w-[200px] appearance-none"
                >
                  <option selected hidden disabled>
                    Filter ({{ filtered.length }})
                  </option>
                  <option>item 1</option>
                  <option>item 2</option>
                  <option>item 3</option>
                </select>
              </div>

              <div
                class="border-2 border-gray-300 rounded-lg overflow-hidden flex"
              >
                <div class="p-1 2xl:p-2 border-r-2 bg-gray-200">
                  <Icons name="gridview" />
                </div>

                <div class="p-1 2xl:p-2 border-l-2">
                  <Icons name="listview" />
                </div>
              </div>
            </div>
          </div>

          <div
            class="w-full py-5 grid 2xl:block auto-cols-max grid-flow-col gap-2 p-5 overflow-scroll 2xl:overflow-hidden"
          >
            <div
              v-for="(el, ind) in filtered"
              class="2xl:inline-block bg-white border-2 border-primary rounded-lg py-1 px-2 m-1 select-none"
            >
              <div class="flex items-center gap-3">
                <h6 class="body">
                  <span> {{ el.name }}</span>
                </h6>

                <div
                  @click="el.checked = false"
                  class="cursor-pointer hover:bg-slate-100 rounded-full"
                >
                  <Icons name="clear" color="#8B96A5" size="16" />
                </div>
              </div>
            </div>

            <div
              v-if="filtered.length"
              @click="filtered.forEach((e) => (e.checked = false))"
              class="inline-block cursor-pointer hover:bg-slate-100 rounded-full mx-5 p-3"
            >
              <div class="flex items-center">
                <h6 class="h6">
                  <span class="text-primary font-normal">Clear all filter</span>
                </h6>
              </div>
            </div>
          </div>

          <div class="grid 2xl:grid-cols-3 gap-5">
            <div
              v-for="(el, ind) in mobile"
              :key="ind"
              class="bg-white border-2 border-gray-300 rounded-lg overflow-hidden mx-5 2xl:mx-0 flex items-center gap-5 2xl:block p-2"
            >
              <div
                class="flex justify-center items-center h-full 2xl:h-auto 2xl:border-b-2 2xl:border-gray-300 flex-shrink-0"
              >
                <img
                  class="w-[80px] 2xl:w-[230px] h-[100px] 2xl:h-[230px] object-cover 2xl:mb-5"
                  :src="`/images/${el.image}`"
                  alt="mobile"
                />
              </div>

              <div class="2xl:p-5">
                <div class="flex justify-between">
                  <div>
                    <div class="flex items-baseline gap-3 mb-1">
                      <h5 class="h5">
                        <span>{{ el.newPrice }}</span>
                      </h5>
                      <h6 class="h6">
                        <span class="text-gray-500 font-normal line-through">{{
                          el.oldPrice
                        }}</span>
                      </h6>
                    </div>

                    <div class="flex items-center gap-2">
                      <div class="flex items-center">
                        <div
                          v-for="(el, ind) in Math.floor(el.rating)"
                          :key="ind"
                          class="flex items-center"
                        >
                          <Icons name="star" color="#FF9017" size="20" />
                        </div>

                        <div
                          v-if="el.rating != Math.floor(el.rating)"
                          class="flex items-center"
                        >
                          <Icons name="star_half" color="#FF9017" size="20" />
                        </div>

                        <div
                          v-if="
                            1 <= 5 - Math.ceil(el.rating) &&
                            el.rating == Math.floor(el.rating)
                          "
                          v-for="(el, ind) in 5 - Math.floor(el.rating)"
                          :key="ind"
                          class="flex items-center"
                        >
                          <Icons name="star_border" color="#FF9017" size="20" />
                        </div>

                        <div
                          v-if="
                            1 <= 5 - Math.ceil(el.rating) &&
                            el.rating != Math.floor(el.rating)
                          "
                          v-for="(el, ind) in 4 - Math.floor(el.rating)"
                          :key="ind"
                          class="flex items-center"
                        >
                          <Icons name="star_border" color="#FF9017" size="20" />
                        </div>
                      </div>

                      <h6 class="body-sm 2xl:body pt-1 2xl:pt-0">
                        <span class="text-orange">{{ el.rating }}</span>
                      </h6>

                      <div
                        class="flex items-center gap-1 2xl:hidden pt-1 2xl:pt-0"
                      >
                        <div class="bg-gray-500 w-1 h-1 rounded-full"></div>

                        <h6 class="body-sm-muted">
                          <span>{{ el.orders }} orders</span>
                        </h6>
                      </div>
                    </div>
                  </div>

                  <div
                    class="hidden w-[37px] h-[37px] 2xl:flex items-center justify-center border-2 border-gray-300 rounded-lg"
                  >
                    <Icons name="favorite_border" color="#0D6EFD" />
                  </div>
                </div>

                <h6 class="h6 2xl:body 2xl:w-[240px] pt-2">
                  <span class="text-gray-600 font-normal">{{
                    el.description
                  }}</span>
                </h6>

                <h6 class="2xl:hidden body w-[240px] pt-2">
                  <span class="text-green">Free shipping</span>
                </h6>
              </div>
            </div>
          </div>

          <div class="flex justify-center 2xl:justify-end my-10">
            <div class="flex items-center gap-2">
              <div class="relative">
                <Icons
                  class="absolute top-[25%] right-2"
                  name="expand_more"
                  color="#8B96A5"
                />
                <select
                  name="pcs"
                  id="pcs"
                  class="font-normal border-2 border-gray-300 rounded-lg w-[110px] p-2 appearance-none"
                >
                  <option value="10" selected>Show 10</option>
                  <option value="20">Show 20</option>
                  <option value="30">Show 30</option>
                  <option value="40">Show 40</option>
                </select>
              </div>

              <div class="h6 flex bg-white border-2 border-gray-300 rounded-lg">
                <div class="flex items-center justify-center p-2 border-r-2">
                  <Icons name="chevron_left" />
                </div>

                <div
                  class="flex items-center justify-center w-[40px] border-r-2"
                >
                  <h6><span>1</span></h6>
                </div>

                <div
                  class="flex items-center justify-center w-[40px] border-r-2"
                >
                  <h6><span>2</span></h6>
                </div>

                <div
                  class="flex items-center justify-center w-[40px] border-r-2"
                >
                  <h6><span>3</span></h6>
                </div>

                <div class="flex items-center justify-center p-2">
                  <Icons name="chevron_right" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
const nav = ref([
  { id: 1, name: "Tablets", link: "/mobile" },
  { id: 2, name: "Phones", link: "/mobile" },
  { id: 3, name: "Ipads", link: "/mobile" },
  { id: 4, name: "Ipod", link: "/mobile" },
  { id: 5, name: "Smart watches", link: "/mobile" },
  { id: 6, name: "Laptops", link: "/mobile" },
]);

const mobile = ref([
  {
    id: 1,
    image: "mobile-image-1.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 4,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 2,
    image: "mobile-image-2.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 4.5,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 3,
    image: "mobile-image-3.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 5,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 4,
    image: "mobile-image-4.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 3.5,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },
  {
    id: 5,
    image: "mobile-image-5.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 3,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 6,
    image: "mobile-image-6.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 2.5,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 7,
    image: "mobile-image-7.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 2,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 8,
    image: "mobile-image-8.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 1.5,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },

  {
    id: 9,
    image: "mobile-image-9.png",
    newPrice: "$99.50",
    oldPrice: "$1128.00",
    rating: 1,
    orders: 154,
    description: "GoPro HERO6 4K Action Camera - Black",
  },
]);

const items = ref(12911);
const page = ref("Mobile accessory");

const filtered = computed(() =>
  filter.value.map((e) => e.items.filter((i) => i.checked)).flat()
);

const filter = ref([
  {
    id: 1,
    isOpen: true,
    name: "Category",
    type: "select",
    items: [
      {
        name: "Mobile accessory",
      },
      {
        name: "Electronics",
      },
      {
        name: "Smartphones",
      },
      {
        name: "Modern tech",
      },
    ],
  },
  {
    id: 2,
    isOpen: true,
    name: "Brands",
    type: "checkbox",
    items: [
      {
        id: 1,
        checked: true,
        name: "Samsung",
      },
      {
        id: 2,
        checked: true,
        name: "Apple",
      },
      {
        id: 3,
        checked: false,
        name: "Huawei",
      },
      {
        id: 4,
        checked: true,
        name: "Pocco",
      },
      {
        id: 5,
        checked: false,
        name: "Lenovo",
      },
    ],
  },
  {
    id: 3,
    isOpen: true,
    name: "Features",
    type: "checkbox",
    items: [
      {
        id: 1,
        checked: true,
        name: "Metallic",
      },
      {
        id: 2,
        checked: false,
        name: "Plastic cover",
      },
      {
        id: 3,
        checked: false,
        name: "8GB Ram",
      },
      {
        id: 4,
        checked: false,
        name: "Super power",
      },
      {
        id: 5,
        checked: false,
        name: "Large Memory",
      },
    ],
  },
  {
    id: 4,
    isOpen: false,
    name: "Price range",
    type: "checkbox",
    items: [
      {
        id: 1,
        checked: false,
        name: "$10",
      },
      {
        id: 2,
        checked: false,
        name: "$10",
      },
      {
        id: 3,
        checked: false,
        name: "$10",
      },
      {
        id: 4,
        checked: false,
        name: "$10",
      },
      {
        id: 5,
        checked: false,
        name: "$10",
      },
    ],
  },
  {
    id: 5,
    isOpen: false,
    name: "Condition",
    type: "checkbox",
    items: [
      {
        id: 1,
        checked: false,
        name: "good",
      },
      {
        id: 2,
        checked: false,
        name: "good",
      },
      {
        id: 3,
        checked: false,
        name: "good",
      },
      {
        id: 4,
        checked: false,
        name: "good",
      },
      {
        id: 5,
        checked: false,
        name: "good",
      },
    ],
  },
  {
    id: 6,
    isOpen: false,
    name: "Ratings",
    type: "checkbox",
    items: [
      {
        id: 1,
        checked: false,
        name: "5 star",
      },
      {
        id: 2,
        checked: true,
        name: "4 star",
      },
      {
        id: 3,
        checked: true,
        name: "3 star",
      },
      {
        id: 4,
        checked: false,
        name: "2 star",
      },
      {
        id: 5,
        checked: false,
        name: "1 star",
      },
    ],
  },
  {
    id: 7,
    isOpen: false,
    name: "Manufacturer",
    type: "checkbox",
    items: [
      {
        id: 1,
        checked: false,
        name: "Apple",
      },
      {
        id: 2,
        checked: false,
        name: "Apple",
      },
      {
        id: 3,
        checked: false,
        name: "Apple",
      },
      {
        id: 4,
        checked: false,
        name: "Apple",
      },
      {
        id: 5,
        checked: false,
        name: "Apple",
      },
    ],
  },
]);
</script>

<style lang="scss" scoped></style>
