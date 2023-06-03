<template>
  <header>
    <Container>
      <nav class="py-5 flex justify-between">
        <nuxt-link to="/"><img src="/icons/logo.svg" alt="logo" /></nuxt-link>

        <div class="flex border-primary border-2 rounded-lg">
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

        <div class="body-mc-muted flex items-center gap-7">
          <div class="flex flex-col gap-1 items-center">
            <Icons name="person_fill" color="#8B96A5" />

            <span class="text-center">Profile</span>
          </div>

          <div class="flex flex-col gap-1 items-center">
            <Icons name="chat_fill" color="#8B96A5" />

            <span class="text-center">Profile</span>
          </div>

          <div class="flex flex-col gap-1 items-center">
            <Icons name="favorite" color="#8B96A5" />

            <span class="text-center">Profile</span>
          </div>

          <div class="flex flex-col gap-1 items-center">
            <Icons name="shopping_cart_fill" color="#8B96A5" />

            <span class="text-center">Profile</span>
          </div>
        </div>
      </nav>
    </Container>

    <div class="h6 border-y-2 border-gray-300">
      <Container>
        <div class="py-5 flex items-center justify-between">
          <div class="flex items-center gap-10">
            <div class="flex items-center gap-3">
              <Icons name="menu" />

              <span>All category</span>
            </div>

            <span>Hot offers</span>

            <span>Gift boxes</span>

            <span>Projects</span>

            <span>Menu item</span>

            <div class="flex items-center cursor-pointer select-none">
              <span>Help</span>

              <Icons name="expand_more" color="#8B96A5" />
            </div>
          </div>

          <div class="flex items-center gap-10">
            <div class="flex items-center cursor-pointer select-none">
              <span>English, USD</span>

              <Icons name="expand_more" color="#8B96A5" />
            </div>

            <div class="flex items-center gap-2 cursor-pointer select-none">
              <span>Ship to</span>

              <Icons name="de" />

              <Icons name="expand_more" color="#8B96A5" />
            </div>
          </div>
        </div>
      </Container>
    </div>
  </header>
</template>

<script setup>
const isOpen = ref(false);

const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style lang="scss" scoped></style>
