<template>
  <header>
    <Container>
      <nav class="py-5 flex justify-between">
        <div
          v-if="useRoute().name == 'index'"
          class="flex items-center gap-5 pl-5 2xl:pl-0"
        >
          <div
            class="2xl:hidden focus:outline-none rounded-full p-1"
            @click="sideOpen = !sideOpen"
          >
            <Icons name="menu" />
          </div>

          <nuxt-link to="/"><img src="/icons/logo.svg" alt="logo" /></nuxt-link>
        </div>

        <div
          v-else-if="useRoute().name != 'index'"
          class="flex items-center gap-2 2xl:gap-5 pl-5 2xl:pl-0"
        >
          <nuxt-link class="p-2 rounded-full" to="/">
            <Icons name="arrow_back" />
          </nuxt-link>

          <h5 class="h5">
            <span>{{
              routes.find((e) => e.path == useRoute().fullPath)?.name
            }}</span>
          </h5>
        </div>

        <div class="flex items-center gap-8 2xl:hidden pr-5">
          <nuxt-link to="/my-cart" class="2xl:hidden p-2 rounded-full">
            <Icons name="shopping_cart" />
          </nuxt-link>

          <Icons name="person" />
        </div>

        <div class="hidden 2xl:flex border-primary border-2 rounded-lg">
          <input
            class="focus:outline-none px-3 w-[500px] rounded-l-lg"
            type="text"
            name="search"
            id="search"
            placeholder="Search"
          />

          <button
            class="dropdown border-l border-primary"
            @click="toggleDropdown"
            @blur="toggleDropdown"
          >
            <div class="h6 flex items-center gap-3 px-3 select-none">
              <span>All category</span>

              <Icons name="expand_more" color="#8B96A5" />
            </div>

            <div class="relative w-full">
              <div
                v-if="isOpen"
                class="dropdown-content absolute top-3 w-full z-10 bg-slate-100"
              >
                <div class="flex items-center p-3 hover:bg-slate-200">
                  <span>item 1</span>
                </div>
                <div class="flex items-center p-3 hover:bg-slate-200">
                  <span>item 1</span>
                </div>
                <div class="flex items-center p-3 hover:bg-slate-200">
                  <span>item 1</span>
                </div>
              </div>
            </div>
          </button>

          <button class="bg-primary text-white px-5 rounded-r">
            <span>Search</span>
          </button>
        </div>

        <div class="hidden body-mc-muted 2xl:flex items-center gap-7">
          <div class="flex flex-col gap-1 items-center">
            <Icons name="person_fill" color="#8B96A5" />

            <span class="text-center">Profile</span>
          </div>

          <div class="flex flex-col gap-1 items-center">
            <Icons name="chat_fill" color="#8B96A5" />

            <span class="text-center">Message</span>
          </div>

          <div class="flex flex-col gap-1 items-center">
            <Icons name="favorite" color="#8B96A5" />

            <span class="text-center">Orders</span>
          </div>

          <nuxt-link to="/my-cart" class="flex flex-col gap-1 items-center">
            <Icons name="shopping_cart_fill" color="#8B96A5" />

            <span class="text-center">My cart</span>
          </nuxt-link>
        </div>
      </nav>

      <div
        class="relative border-2 border-gray-300 rounded-lg overflow-hidden mx-5 2xl:hidden"
      >
        <Icons class="absolute top-3 left-4" name="search" color="#8B96A5" />

        <input
          type="text"
          class="py-3 pl-14 focus:outline-none"
          placeholder="Search"
        />
      </div>
    </Container>
  </header>

  <aside
    v-if="sideOpen"
    class="top-0 left-0 h-screen w-full bg-black bg-opacity-60 z-30 fixed"
  >
    <div class="flex h-full">
      <div class="w-[300px] flex-shrink-0 bg-white">
        <div class="bg-gray-200 p-5">
          <img src="/icons/avatar.svg" alt="user" />

          <div class="mt-5">
            <h6 class="h6">
              <span class="font-normal">Sign in | Register</span>
            </h6>
          </div>
        </div>

        <div class="p-2">
          <div class="flex items-center gap-3 p-3">
            <Icons name="home" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">Home</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3">
            <Icons name="list" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">Categories</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3">
            <Icons name="favorite_border" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">Favorites</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3 border-b-2 pb-5">
            <Icons name="inventory_2" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">My orders</span>
            </h6>
          </div>
        </div>

        <div class="p-2">
          <div class="flex items-center gap-3 p-3">
            <Icons name="language" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">English | USD</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3">
            <Icons name="headset_mic" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">Contact us</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3 border-b-2 pb-5">
            <Icons name="business" color="#8B96A5" />

            <h6 class="h6">
              <span class="font-normal">About</span>
            </h6>
          </div>
        </div>

        <div class="p-2 pl-10">
          <div class="flex items-center gap-3 p-3">
            <h6 class="h6">
              <span class="font-normal">User agreement</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3">
            <h6 class="h6">
              <span class="font-normal">Partnership</span>
            </h6>
          </div>

          <div class="flex items-center gap-3 p-3">
            <h6 class="h6">
              <span class="font-normal">Privacy policy</span>
            </h6>
          </div>
        </div>
      </div>

      <div
        class="w-full h-full bg-black bg-opacity-0"
        @click="sideOpen = !sideOpen"
      ></div>
    </div>
  </aside>
</template>

<script setup>
const sideOpen = ref(false);

const routes = ref([
  { id: 1, name: "Mobile accessory", path: "/mobile" },
  { id: 2, name: "Shopping cart", path: "/my-cart" },
  { id: 3, name: "Icons", path: "/icons/" },
]);

const isOpen = ref(false);

const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style lang="scss" scoped></style>
