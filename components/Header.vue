<template>
  <header>
    <Container>
      <nav class="py-5 flex justify-between">
        <div class="flex items-center gap-5 pl-5">
          <div>
            <Icons name="menu" />
          </div>

          <nuxt-link to="/"><img src="/icons/logo.svg" alt="logo" /></nuxt-link>
        </div>

        <div class="flex items-center gap-8 2xl:hidden pr-5">
          <Icons name="shopping_cart" />

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
</template>

<script setup>
const isOpen = ref(false);

const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style lang="scss" scoped></style>
