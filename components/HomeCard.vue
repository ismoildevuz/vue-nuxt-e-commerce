<template>
  <div
    class="border-2 2xl:border-l-2 2xl:border-y 2xl:border-r-0 border-gray-300 p-5 relative"
  >
    <div
      class="w-[100px] 2xl:w-auto flex justify-center 2xl:block 2xl:absolute 2xl:bottom-1 2xl:right-1 mb-3 2xl:mb-0"
    >
      <img
        class="w-[82px] h-[82px] object-cover"
        :src="`/images/${el.image}`"
        alt="home"
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
</template>

<script setup>
const props = defineProps(["el"]);
</script>

<style lang="scss" scoped></style>
