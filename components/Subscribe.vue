<template>
  <section class="subscribe bg-gray-200 py-10 hidden 2xl:block">
    <Contaier>
      <div class="mx-auto w-[600px]">
        <div class="text-center">
          <h4 class="h4"><span>Subscribe on our newsletter</span></h4>
          <h4 class="body">
            <span
              >Get daily news on upcoming offers from many suppliers all over
              the world</span
            >
          </h4>
        </div>

        <div class="flex items-center justify-center gap-2 mt-5">
          <div class="relative">
            <Icons
              name="email"
              color="#8B96A5"
              class="absolute top-[10px] left-2"
            />
            <input
              type="text"
              class="pl-9 py-2 rounded-lg border-2 border-gray-300 focus:outline-none"
              placeholder="Email"
            />
          </div>

          <button class="px-3 py-2 bg-primary rounded-lg">
            <span class="text-white font-medium"> Subscibe </span>
          </button>
        </div>
      </div>
    </Contaier>
  </section>
</template>

<script setup></script>

<style lang="scss" scoped></style>
