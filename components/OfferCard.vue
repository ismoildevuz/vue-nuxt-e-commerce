<template>
  <div class="border-2 2xl:border-0 2xl:border-l-2 border-gray-300 p-5">
    <div
      class="w-[130px] 2xl:w-auto flex flex-shrink-0 justify-center 2xl:block"
    >
      <img
        class="w-[100px] 2xl:w-[210px] h-[100px] 2xl:h-[210px] object-cover"
        :src="`/images/${el.image}`"
        alt="offer"
      />
    </div>

    <div class="text-center">
      <h5 class="body-sm 2xl:h5 my-3">
        <span class="text-dark 2xl:font-normal">{{ el.name }}</span>
      </h5>

      <h6 class="h6 inline-block text-red bg-[#FFE3E3] px-3 py-2 rounded-full">
        <span class="font-medium">{{ el.offer }}</span>
      </h6>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
